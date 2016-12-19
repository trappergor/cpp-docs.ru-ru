---
title: "CTypedPtrList Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTypedPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTypedPtrList class"
  - "linked lists [C++]"
  - "lists [C++]"
  - "pointer lists"
  - "template classes, CTypedPtrList class"
  - "type-safe collections"
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTypedPtrList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет типобезопасную "программу\-оболочку" для объектов класса `CPtrList`.  
  
## Синтаксис  
  
```  
template< class BASE_CLASS, class TYPE >  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### Параметры  
 `BASE_CLASS`  
 Базовый класс типизированного класса списка указателя. должен быть классом списка указателя " \(`CObList` или `CPtrList`\).  
  
 `TYPE`  
 Тип элементов, хранящихся в списке базового класса.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CTypedPtrList::AddHead](../Topic/CTypedPtrList::AddHead.md)|Добавляет элемент \(или все элементы в других список\) в начало списка \(делает новую головку\).|  
|[CTypedPtrList::AddTail](../Topic/CTypedPtrList::AddTail.md)|Добавляет элемент \(или все элементы в других список\) в кабелю списка \(делает новый хвост\).|  
|[CTypedPtrList::GetAt](../Topic/CTypedPtrList::GetAt.md)|Возвращает элемент на заданной позиции.|  
|[CTypedPtrList::GetHead](../Topic/CTypedPtrList::GetHead.md)|Возвращает головной элемент списка \(не может быть пустым\).|  
|[CTypedPtrList::GetNext](../Topic/CTypedPtrList::GetNext.md)|Возвращает следующий элемент для итерации.|  
|[CTypedPtrList::GetPrev](../Topic/CTypedPtrList::GetPrev.md)|Возвращает предыдущий элемент для итерации.|  
|[CTypedPtrList::GetTail](../Topic/CTypedPtrList::GetTail.md)|Возвращает элемент списка с префиксом tail \(не может быть пустым\).|  
|[CTypedPtrList::RemoveHead](../Topic/CTypedPtrList::RemoveHead.md)|Удаляет элемент из списка head.|  
|[CTypedPtrList::RemoveTail](../Topic/CTypedPtrList::RemoveTail.md)|Удаляет элемент из списка с префиксом tail.|  
|[CTypedPtrList::SetAt](../Topic/CTypedPtrList::SetAt.md)|Задает элемент по заданной позиции.|  
  
## Заметки  
 При использовании `CTypedPtrList`, а не `CObList` или `CPtrList`, средства проверки типа C\+\+ кроме ошибки, вызванные рассогласованными типами указателя.  
  
 Кроме того, программа\-оболочка `CTypedPtrList` выполняет многие приведения, необходимой при использовании `CObList` или `CPtrList`.  
  
 Поскольку все функции `CTypedPtrList` встроенным использование данного шаблона в значительной степени не влияет на размер или скорости кода.  
  
 Списки, производные от `CObList` может быть сериализован, но эти производные от `CPtrList` не могут.  
  
 Если объект `CTypedPtrList` удаления или при его элементы удалены указатели, а не только удалены сущности, на который они ссылаются.  
  
 Дополнительные сведения об использовании `CTypedPtrList` см. в разделе статьи [коллекции](../../mfc/collections.md) и [Шаблон\- на основе классов](../Topic/Template-Based%20Classes.md).  
  
## Пример  
 В этом примере создается экземпляр `CTypedPtrList` добавляет один объект сериализует список на диск, а затем удаляет объект.  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/CPP/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/CPP/ctypedptrlist-class_2.cpp)]  
  
## Иерархия наследования  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## Требования  
 **Header:**  afxtempl.h  
  
## См. также  
 [Образец MFC СОБИРАЕТ](../../top/visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CPtrList Class](../Topic/CPtrList%20Class.md)   
 [CObList Class](../../mfc/reference/coblist-class.md)