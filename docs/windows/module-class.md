---
title: "Класс Module | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module
dev_langs: C++
helpviewer_keywords: Module class
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b2536d406293d84db2ce5d5bd3e0292e0e57920e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="module-class"></a>Module - класс
Представляет коллекцию связанных объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `moduleType`  
 Сочетание одного или нескольких [ModuleType](../windows/moduletype-enumeration.md) значений перечисления.  
  
## <a name="members"></a>Члены  
  
### <a name="protected-classes"></a>Защищенные классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.|  
|[Класс Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его элементом указателя для метода.|  
|[Класс Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)|Вызывает обработчик событий при освобождении последнего объекта в модуле.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Деструктор Module::~Module](../windows/module-tilde-module-destructor.md)|Деинициализирует текущий экземпляр класса Module.|  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор Module::Module](../windows/module-module-constructor.md)|Инициализирует новый экземпляр класса Module.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Module::Create](../windows/module-create-method.md)|Создает экземпляр модуля.|  
|[Метод Module::DecrementObjectCount](../windows/module-decrementobjectcount-method.md)|Уменьшает число объектов, отслеживаемых модулем.|  
|[Метод Module::GetActivationFactory](../windows/module-getactivationfactory-method.md)|Получает фабрику активации для модуля.|  
|[Метод Module::GetClassObject](../windows/module-getclassobject-method.md)|Извлекает кэш фабрик классов.|  
|[Метод Module::GetModule](../windows/module-getmodule-method.md)|Создает экземпляр модуля.|  
|[Метод Module::GetObjectCount](../windows/module-getobjectcount-method.md)|Извлекает количество объектов, управляемых этим модулем.|  
|[Метод Module::IncrementObjectCount](../windows/module-incrementobjectcount-method.md)|Увеличивает число объектов, отслеживаемых модулем.|  
|[Метод Module::RegisterCOMObject](../windows/module-registercomobject-method.md)|Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.|  
|[Метод Module::RegisterObjects](../windows/module-registerobjects-method.md)|Регистрирует объекты COM или среды выполнения Windows, чтобы другие приложения могли к ним подключиться.|  
|[Метод Module::RegisterWinRTObject](../windows/module-registerwinrtobject-method.md)|Регистрирует один или несколько объектов среды выполнения Windows, чтобы другие приложения могли к ним подключиться.|  
|[Метод Module::Terminate](../windows/module-terminate-method.md)|Приводит к завершению работы всех экземпляров фабрик, созданных модулем.|  
|[Метод Module::UnregisterCOMObject](../windows/module-unregistercomobject-method.md)|Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.|  
|[Метод Module::UnregisterObjects](../windows/module-unregisterobjects-method.md)|Отменяет регистрацию объектов в указанном модуле. Таким образом другие приложения не смогут подключиться к ним.|  
|[Метод Module::UnregisterWinRTObject](../windows/module-unregisterwinrtobject-method.md)|Отменяет регистрацию одного или нескольких объектов среды выполнения Windows, чтобы другие приложения не смогут подключиться к ним.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Module::Create](../windows/module-create-method.md)|Создает экземпляр модуля.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных Module::objectCount_](../windows/module-objectcount-data-member.md)|Хранит список количества классов были созданы при помощи [сделать](../windows/make-function.md) функции.|  
|[Элемент данных Module::releaseNotifier_](../windows/module-releasenotifier-data-member.md)|Содержит указатель на объект ReleaseNotifier.|  
  
### <a name="macros"></a>Макросы  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|Заполняет внутренний кэш, который содержит фабрику, можно создать экземпляр указанного класса. Этот макрос задает параметры идентификатора фабрики и группы по умолчанию.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Заполняет внутренний кэш, который содержит фабрику, можно создать экземпляр указанного класса. Этот макрос позволяет задать параметр конкретного фабрики.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Заполняет внутренний кэш, который содержит фабрику, можно создать экземпляр указанного класса. Этот макрос можно указать определенный фабрики и параметры идентификатора группы.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)