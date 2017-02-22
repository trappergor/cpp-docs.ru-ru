---
title: "CComEnumOnSTL Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComEnumOnSTL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumOnSTL class"
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComEnumOnSTL Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс определяет объект перечислителя модели COM на основе коллекций STL.  
  
## Синтаксис  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType,  
   class ThreadModel = CComObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnumOnSTL :  
   public IEnumOnSTLImpl<Base, piid, T, Copy, CollType>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### Параметры  
 `Base`  
 Интерфейс перечислителя модели COM \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\).  
  
 `piid`  
 Указатель на идентификатор интерфейса интерфейса перечислителя.  
  
 `T`  
 Тип элемента, предоставляемый интерфейсом перечислителя.  
  
 `Copy`  
 Класс [политика копии](../Topic/ATL%20Copy%20Policy%20Classes.md).  
  
 `CollType`  
 Класс контейнеров STL.  
  
## Заметки  
 `CComEnumOnSTL` определяет объект перечислителя модели COM на основе коллекций STL.  Этот класс может использоваться отдельно или совместно с [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  Типичные действия по использованию этого класса конспектированы ниже.  Дополнительные сведения см. в разделе [Коллекции и перечислители библиотеки ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Чтобы использовать этот класс, ICollectionOnSTLImpl:  
  
-   `typedef` специализация класса.  
  
-   Используйте `typedef` как последний аргумент шаблона в специализации `ICollectionOnSTLImpl`.  
  
 См. раздел [Коллекции и перечислители библиотеки ATL](../../atl/atl-collections-and-enumerators.md) для примера.  
  
## Использовать этот класс, независимо от ICollectionOnSTLImpl:  
  
-   `typedef` специализация класса.  
  
-   Используйте `typedef` в качестве аргумента шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр `CComObject` специализации.  
  
-   Инициализируйте объект путем вызова [IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md) перечислителя.  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## Требования  
 **Header:**  atlcom.h  
  
## Пример  
 Код, показанный ниже предоставляет универсальную функцию для обработки создание и инициализация объекта перечислителя.  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/CPP/ccomenumonstl-class_1.h)]  
  
 Эту функцию шаблона можно использовать для реализации свойство `_NewEnum` интерфейса коллекции, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/CPP/ccomenumonstl-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnumOnSTL`, который представляет вектор `CComVariant` s посредством интерфейса **IEnumVariant**.  Класс **CVariantCollection** просто специализирует **CreateSTLEnumerator** для работы с объектами перечислителя данного типа.  
  
## См. также  
 [Образец ATLCollections: Демонстрация ICollectionOnSTLImpl, CComEnumOnSTL и пользовательских классов политики копирования](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)   
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)