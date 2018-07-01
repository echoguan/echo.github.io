---
title: Facade Design Pattern
categories: 技术
date: 2018-06-29 10:18:08
tags:
---

#### Facade  外观模式/门面模式

##### 作用

- The intent of the Facade is to provide a high-level interface (properties and methods) that makes a subsystem or toolkit easy to use for the client. 

  统一入口，简化调用

- The Facade exposes only what is necessary and presents a cleaner and easy-to-use interface. 

- 降低依赖，松耦合

##### 应用场景

- It is often present in systems that are built around a multi-layer architecture. 
- Facades themselves are often implemented as singleton factories. 

##### Diagram

![Diagram JavaScript Facade  Design Pattern](https://www.dofactory.com/images/diagrams/javascript/javascript-facade.jpg) 

##### 代码结构

1. `FacadeFactory` - Facade 工厂

   调用`ClassController`和`Confiration`，创建各种需要的 Facade 接口。

2. `ClassController`

   读取 configuration 配置文件，取到相应的 Wrapper。

3. `Configuration` - 配置文件

   

##### Sample Code

1. `RatedDriverListWrapper`

   ```javascript
   // 1.方法中调用了 Facade
   _isRatedDriver(driver) {
       const state = this._getQuoteStore().getState();
       // 2.创建相应的 Facade 实例 -> ②
       const driverTypeFacades = FacadeFactory.getDriverKindFacade(state);
       return (
           driver.DriverInfo &&
           driver.Selected &&
           // 12.得到相应的 Facade 实例后，调用方法完成需求
           !driverTypeFacades.isExcludedDriver(driver) &&
           !driverTypeFacades.isPermittedDriver(driver)
       );
   }
   ```

2. `FacadeFactory`

   ```javascript
   import appConstants from "../constants/app-constants";
   import configuration from "./Configuration";
   import Controller from "./ClassController";
   
   // 3.Facade Factory
   class FacadeFactory {
       constructor() {
           // ClassController -> ③ && Configuration -> ④
           this._controller = new Controller(configuration);
       }
   
       // 5.具体填充方法
       _populateTarget(state, name) {
           // 6.调用 ClassController 完成填充 -> ③
           return this._controller.getTarget(state, {
               func: name
           });
       }
   
       // 4.创建 DriverKindFacade
       getDriverKindFacade(state) {
           // 11.得到对应的 Wrapper, 即 DriverKindFacade
           const Facade = this._populateTarget(
               state,
               appConstants.FACADE_DRIVER_KIND
           );
           return new Facade();
       }
       
       ...
   }
   ```

3. `ClassController`

   ```javascript
   class ClassController {
       constructor(configuration) {
           this._initialize(configuration);
       }
   
       // 7.初始化，读取 configuration 配置文件信息
       _initialize(configuration) {
           const context = new BaseControllerContext();
           context.read(configuration);
           this._context = context;
       }
   
       // 10.通过配置文件，取到相应的 Wrapper，即 DriverKindFacade（不同的 state 可能对应不同的 Facade）
       _populateTarget(metadata) {
           let wrapper = null;
           if (metadata && metadata.getWrapper()) {
               wrapper = metadata.getWrapper();
           }
           return wrapper;
       }
   
       // 9.state - store
       //   item - func name, eg: FACADE_DRIVER_KIND
       getTarget(state, item) {
           const metadata = this._context.getMetadata(state, {}, item);
           return this._populateTarget(metadata, item);
       }
   }
   
   export default ClassController;
   ```

4. `Configuration` - 配置文件

   ```javascript
   // 8.不同的 state 的 FACADE_DRIVER_KIND 可能对应不同的 Facade 文件
   const config = {
       DefaultFilter: require("../components/Common/BaseFilters/FunctionFilter"),
       DefaultWrappers: {
           Common: [
               {
                   func: appConstants.FACADE_DRIVER_KIND,
                   wrapper: require("./BaseDriverKindFacade")
               },
               
               ...
           ]
       },
       SpecialWrappers: {
           PA: [
               {
                   func: appConstants.FACADE_DRIVER_KIND,
                   wrapper: require("./PA/DriverKindFacade")
               },
               
               ...
           ],
           VT: [
               ...
           ],
           NH: [
               ...
           ],
           ME: [
               ...
           ],
           MO: [
               ...
           ]
       }
   };
   ```

   



##### Reference

> [facade-design-pattern](https://www.dofactory.com/javascript/facade-design-pattern)