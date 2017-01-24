---
title: "Класс Module | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module - класс"
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс Module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет коллекцию связанных объектов.  
  
## Синтаксис  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### Параметры  
 `moduleType`  
 Сочетание одного или нескольких значений перечисления [ModuleType](../Topic/ModuleType%20Enumeration.md).  
  
## Члены  
  
### Защищенные классы  
  
|Имя|Описание|  
|---------|--------------|  
|[Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле.  Обработчик событий определяется в лямбда\-выражении, функтором или указателем\-на\-функцию.|  
|[Класс Module::MethodReleaseNotifier](../Topic/Module::MethodReleaseNotifier%20Class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле.  Обработчик событий определяется объектом и его членом\-указателем\-на\-метод.|  
|[Класс Module::ReleaseNotifier](../Topic/Module::ReleaseNotifier%20Class.md)|Вызывает обработчик событий при освобождении последнего объекта в модуле.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Деструктор Module::~Module](../windows/module-tilde-module-destructor.md)|Деинициализирует текущий экземпляр класса Module.|  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор Module::Module](../windows/module-module-constructor.md)|Инициализирует новый экземпляр класса Module.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Module::Create](../windows/module-create-method.md)|Создает экземпляр модуля.|  
|[Метод Module::DecrementObjectCount](../windows/module-decrementobjectcount-method.md)|Уменьшает количество объектов, отслеживаемых модулем.|  
|[Метод Module::GetActivationFactory](../windows/module-getactivationfactory-method.md)|Получает фабрику активации для модуля.|  
|[Метод Module::GetClassObject](../windows/module-getclassobject-method.md)|Извлекает кэш фабрик классов.|  
|[Метод Module::GetModule](../Topic/Module::GetModule%20Method.md)|Создает экземпляр модуля.|  
|[Метод Module::GetObjectCount](../windows/module-getobjectcount-method.md)|Извлекает количество объектов, управляемых этим модулем.|  
|[Метод Module::IncrementObjectCount](../windows/module-incrementobjectcount-method.md)|Увеличивает количество объектов, отслеживаемых модулем.|  
|[Метод Module::RegisterCOMObject](../windows/module-registercomobject-method.md)|Регистрирует один или несколько объектов модели COM таким образом, что другие приложения смогут подключиться к ним.|  
|[Метод Module::RegisterObjects](../windows/module-registerobjects-method.md)|Регистрирует объекты модели COM или [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] таким образом, что другие приложения смогут подключиться к ним.|  
|[Метод Module::RegisterWinRTObject](../windows/module-registerwinrtobject-method.md)|Регистрирует один или несколько объектов [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] таким образом, что другие приложения смогут подключиться к ним.|  
|[Метод Module::Terminate](../windows/module-terminate-method.md)|Приводит к завершению работы всех экземпляров фабрик, созданных модулем.|  
|[Метод Module::UnregisterCOMObject](../Topic/Module::UnregisterCOMObject%20Method.md)|Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.|  
|[Метод Module::UnregisterObjects](../windows/module-unregisterobjects-method.md)|Отменяет регистрацию объектов в указанном модуле таким образом, что другие приложения не смогут подключиться к ним.|  
|[Метод Module::UnregisterWinRTObject](../windows/module-unregisterwinrtobject-method.md)|Отменяет регистрацию одно или несколько объектов [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] таким образом, что другие приложения не смогут подключиться к ним.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Module::Create](../windows/module-create-method.md)|Создает экземпляр модуля.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных Module::objectCount\_](../windows/module-objectcount-data-member.md)|Отслеживает количество классов, созданных функцией [Make](../windows/make-function.md).|  
|[Элемент данных Module::releaseNotifier\_](../windows/module-releasenotifier-data-member.md)|Сохраняет указатель на объект ReleaseNotifier.|  
  
### Макросы  
  
|||  
|-|-|  
|[ActivatableClass](../Topic/ActivatableClass%20Macros.md)|Заполняет внутренний кэш, который содержит фабрику, которая может создать экземпляр указанного класса.  Этот макрос указывает фабрику по умолчанию и параметры идентификатора группы.|  
|[ActivatableClassWithFactory](../Topic/ActivatableClass%20Macros.md)|Заполняет внутренний кэш, который содержит фабрику, которая может создать экземпляр указанного класса.  Этот макрос позволяет указать определенный параметр фабрики.|  
|[ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md)|Заполняет внутренний кэш, который содержит фабрику, которая может создать экземпляр указанного класса.  Этот макрос позволяет указать определенные параметры фабрики и идентификатора группы.|  
  
## Иерархия наследования  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)