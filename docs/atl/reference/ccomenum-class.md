---
title: "CComEnum Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComEnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnum class"
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComEnum Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс определяет объект перечислителя модели COM на основе массива.  
  
## Синтаксис  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class ThreadModel = CcomObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnum :  
   public CComEnumImpl<Base, piid, T, Copy>,  
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
 Однотиповое [скопируйте класс политик](../Topic/ATL%20Copy%20Policy%20Classes.md).  
  
 `ThreadModel`  
 Потоковая модель класса.  Этот параметр имеет значение по умолчанию к глобальным модели потока объекта, используемой в проекте.  
  
## Заметки  
 `CComEnum` определяет объект перечислителя модели COM на основе массива.  Этот класс аналогичн к [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), который реализует перечислитель на основе контейнере STL.  Типичные действия по использованию этого класса конспектированы ниже.  Дополнительные сведения см. в разделе [Коллекции и перечислители библиотеки ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Использовать этот класс.  
  
-   `typedef` специализация класса.  
  
-   Используйте `typedef` в качестве аргумента шаблона в специализации `CComObject`.  
  
-   Создайте экземпляр `CComObject` специализации.  
  
-   Инициализируйте объект путем вызова [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) перечислителя.  
  
-   Возвращает интерфейс перечислителя клиенту.  
  
## Иерархия наследования  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## Требования  
 **Header:**  atlcom.h  
  
## Пример  
 Код, показанный ниже приведены многоразовую функцию для создания и инициализации объект перечислителя.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/CPP/ccomenum-class_1.h)]  
  
 Эту функцию шаблона можно использовать для реализации свойство `_NewEnum` интерфейса коллекции, как показано ниже:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/CPP/ccomenum-class_2.h)]  
  
 Этот код создает `typedef` для `CComEnum`, который представляет вектор **VARIANT** s через интерфейс **IEnumVariant**.  Класс **CVariantArrayCollection** просто специализирует **CreateEnumerator** для работы с объектами перечислителя этого типа и передающий необходимые аргументы.  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [CComEnumImpl Class](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)