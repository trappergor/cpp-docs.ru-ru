---
title: "IDispatchImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispatchImpl"
  - "ATL.IDispatchImpl"
  - "ATL::IDispatchImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "сдвоенные интерфейсы, classes"
  - "IDispatch - поддержка класса в ATL"
  - "IDispatchImpl - класс"
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# IDispatchImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию по умолчанию для части `IDispatch` повторяющегося интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
template<  
   class T,  
   const IID* piid= &__uuidof(T),  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>   
class ATL_NO_VTABLE IDispatchImpl :  
   public T  
```  
  
#### Параметры  
 \[входящий\] `T`  
 Сдвоенный интерфейс.  
  
 \[входящий\] `piid`  
 Указатель на идентификатор IID `T`.  
  
 \[входящий\] `plibid`  
 Указатель на идентификатор LIBID библиотеки типов, содержащий сведения об интерфейсе.  По умолчанию на уровне сервера библиотеки типов при передаче.  
  
 \[входящий\] `wMajor`  
 Основной номер версии библиотеки типов.  По умолчанию значение равно 1.  
  
 \[входящий\] `wMinor`  
 Дополнительный номер версии библиотеки типов.  По умолчанию значение равно 0.  
  
 \[входящий\] `tihclass`  
 Класс, используемый для управления сведения о типе для `T`.  Значение по умолчанию — `CComTypeInfoHolder`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispatchImpl::IDispatchImpl](../Topic/IDispatchImpl::IDispatchImpl.md)|Конструктор.  Вызывает `AddRef` в защищенной переменной члена, которая управляет сведения о типе для двойного интерфейса.  Деструктор вызывается `Release`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IDispatchImpl::GetIDsOfNames](../Topic/IDispatchImpl::GetIDsOfNames.md)|Сопоставляет набор имен соответствующему набору идентификаторов диспетчеризации.|  
|[IDispatchImpl::GetTypeInfo](../Topic/IDispatchImpl::GetTypeInfo.md)|Возвращает сведения о типе повторяющегося интерфейса.|  
|[IDispatchImpl::GetTypeInfoCount](../Topic/IDispatchImpl::GetTypeInfoCount.md)|Определяет, является ли доступным сведений о типе для двойного интерфейса.|  
|[IDispatchImpl::Invoke](../Topic/IDispatchImpl::Invoke.md)|Предоставляет доступ к методам и свойствам со схожими именами, предоставляемым интерфейсом double.|  
  
## Заметки  
 `IDispatchImpl` предоставляет реализацию по умолчанию для части `IDispatch` любого повторяющегося интерфейса на объект.  Сдвоенный интерфейс является производным от `IDispatch` и использует только типы Автоматизация\- совместимости.  Например, диспетчерский интерфейс, сдвоенный интерфейс поддерживает раннее связывание и позднее связывание; однако сдвоенный интерфейс поддерживает также привязку vtable.  
  
 В следующем примере показана типичная реализация метода `IDispatchImpl`:  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/CPP/idispatchimpl-class_1.h)]  
  
 По умолчанию класс `IDispatchImpl` ищет сведения о типе для `T` в реестре.  Для реализации незарегистрированный интерфейс можно использовать класс `IDispatchImpl` без обращения к реестру с помощью предопределенного номера версии.  При создании объекта, `IDispatchImpl`, имеющий 0xFFFF в качестве значения для `wMajor` и 0xFFFF в качестве значения для `wMinor`, класс `IDispatchImpl` извлекает библиотеку типов из dll\-файла вместо реестра.  
  
 `IDispatchImpl` содержащий статический член типа `CComTypeInfoHolder`, который управляет сведения о типе для двойного интерфейса.  Если имеется несколько объектов, которые реализуют один и тот же сдвоенный интерфейс существует только один экземпляр `CComTypeInfoHolder` используется.  
  
## Иерархия наследования  
 `T`  
  
 `IDispatchImpl`  
  
## Требования  
 **заголовок:** atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)