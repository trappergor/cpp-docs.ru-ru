---
title: "IProvideClassInfo2Impl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IProvideClassInfo2"
  - "ATL.IProvideClassInfo2Impl"
  - "IProvideClassInfo2Impl"
  - "ATL::IProvideClassInfo2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class information, ATL - библиотека"
  - "IProvideClassInfo2 ATL implementation"
  - "IProvideClassInfo2Impl class"
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IProvideClassInfo2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию по умолчанию для методов [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) и [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764).  
  
## Синтаксис  
  
```  
  
      template <  
   const CLSID* pcoclsid,  
   const IID* psrcid,  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>  
class ATL_NO_VTABLE IProvideClassInfo2Impl :  
   public IProvideClassInfo2  
```  
  
#### Параметры  
 *pcoclsid*  
 Указатель на идентификатор компонентного класса.  
  
 *psrcid*  
 Указатель на идентификатор для диспетчерский интерфейс компонентного класса по умолчанию исходящего.  
  
 `plibid`  
 Указатель на идентификатор LIBID библиотеки типов, содержащий сведения об интерфейсе.  По умолчанию на уровне сервера библиотеки типов при передаче.  
  
 `wMajor`  
 Основной номер версии библиотеки типов.  Значение по умолчанию \- 1.  
  
 `wMinor`  
 Дополнительный номер версии библиотеки типов.  Значение по умолчанию \- 0.  
  
 `tihclass`  
 Класс, используемый для управления сведения о типе компонентного класса.  Значение по умолчанию — `CComTypeInfoHolder`.  
  
## Члены  
  
### Конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](../Topic/IProvideClassInfo2Impl::IProvideClassInfo2Impl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IProvideClassInfo2Impl::GetClassInfo](../Topic/IProvideClassInfo2Impl::GetClassInfo.md)|Извлекает указатель **ITypeInfo** к информации о типе компонентного класса.|  
|[IProvideClassInfo2Impl::GetGUID](../Topic/IProvideClassInfo2Impl::GetGUID.md)|Получает GUID для исходящего диспетчерский интерфейс объекта.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[IProvideClassInfo2Impl::\_tih](../Topic/IProvideClassInfo2Impl::_tih.md)|Управляет сведения о типе для компонентного класса.|  
  
## Заметки  
 Интерфейс [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) расширяет [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) путем добавления метода `GetGUID`.  Этот метод позволяет клиенту получить интерфейс IID исходящего для объекта по умолчанию набора событий.  Класс `IProvideClassInfo2Impl` предоставляет реализацию по умолчанию для методов **IProvideClassInfo** и `IProvideClassInfo2`.  
  
 `IProvideClassInfo2Impl` содержащий статический член типа `CComTypeInfoHolder`, который управляет сведения о типе для компонентного класса.  
  
## Иерархия наследования  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)