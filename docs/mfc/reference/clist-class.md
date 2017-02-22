---
title: "CList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CList class"
  - "списки"
  - "списки, base class for"
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает упорядоченные списки доступных неуникального объектов, последовательно или значением.  
  
## Синтаксис  
  
```  
template< class TYPE, class ARG_TYPE = const TYPE& >   
class CList : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CList::CList](../Topic/CList::CList.md)|Создает пустой упорядоченный список.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CList::AddHead](../Topic/CList::AddHead.md)|Добавляет элемент \(или все элементы в других список\) в начало списка \(делает новую головку\).|  
|[CList::AddTail](../Topic/CList::AddTail.md)|Добавляет элемент \(или все элементы в других список\) в кабелю списка \(делает новый хвост\).|  
|[CList::Find](../Topic/CList::Find.md)|Получает положение элемента, заданного значением указателя.|  
|[CList::FindIndex](../Topic/CList::FindIndex.md)|Получает положение элемента, указанного на нулевой\- индексу.|  
|[CList::GetAt](../Topic/CList::GetAt.md)|Возвращает элемент на заданной позиции.|  
|[CList::GetCount](../Topic/CList::GetCount.md)|Получает число элементов в данном списке.|  
|[CList::GetHead](../Topic/CList::GetHead.md)|Возвращает головной элемент списка \(не может быть пустым\).|  
|[CList::GetHeadPosition](../Topic/CList::GetHeadPosition.md)|Возвращает позицию головного элемента списка.|  
|[CList::GetNext](../Topic/CList::GetNext.md)|Возвращает следующий элемент для итерации.|  
|[CList::GetPrev](../Topic/CList::GetPrev.md)|Возвращает предыдущий элемент для итерации.|  
|[CList::GetSize](../Topic/CList::GetSize.md)|Получает число элементов в данном списке.|  
|[CList::GetTail](../Topic/CList::GetTail.md)|Возвращает элемент списка с префиксом tail \(не может быть пустым\).|  
|[CList::GetTailPosition](../Topic/CList::GetTailPosition.md)|Возвращает позицию элемента с префиксом tail списка.|  
|[CList::InsertAfter](../Topic/CList::InsertAfter.md)|Вставляет новый элемент после заданной позиции.|  
|[CList::InsertBefore](../Topic/CList::InsertBefore.md)|Вставляет новый элемент до заданной позиции.|  
|[CList::IsEmpty](../Topic/CList::IsEmpty.md)|Тесты для пустого состояния списка \(без элементов\).|  
|[CList::RemoveAll](../Topic/CList::RemoveAll.md)|Удаляет все элементы из этого списка.|  
|[CList::RemoveAt](../Topic/CList::RemoveAt.md)|Удаляет элемент из этого списка, указанного по позиции.|  
|[CList::RemoveHead](../Topic/CList::RemoveHead.md)|Удаляет элемент из списка head.|  
|[CList::RemoveTail](../Topic/CList::RemoveTail.md)|Удаляет элемент из списка с префиксом tail.|  
|[CList::SetAt](../Topic/CList::SetAt.md)|Задает элемент по заданной позиции.|  
  
#### Параметры  
 `TYPE`  
 Тип объекта, хранимого в списке.  
  
 `ARG` *\_* `TYPE`  
 Тип, используемый для ссылки на объекты, хранящиеся в списке.  Может быть ссылкой.  
  
## Заметки  
 Списки `CList` аналогично поведению двойной\- связанные списки.  
  
 Переменная типа **POSITION** ключ для списка.  Можно использовать переменную **POSITION** в виде итератора для просмотра списка последовательно и как закладка, чтобы сохранить место.  Позиция не то же, что и индекс.  
  
 Вставка элемента очень быстро в начало списка на кабеле и в известном **POSITION**.  Последовательный поиск необходим для поиска элемента по значению или по индексу.  Этот поиск может быть медленным, если список длинный.  
  
 Если требуется дамп отдельных элементов в списке, необходимо установить глубину контекста дампа значение 1 или больше.  
  
 Некоторые функции\-члены этого класса вызывают глобальные вспомогательные функции, необходимые для настройки для большинства польз класса `CList`.  См. раздел [Вспомогательные объекты класса коллекции](../../mfc/reference/collection-class-helpers.md) в разделе "Макросы и глобальные переменные".  
  
 Дополнительные сведения об использовании `CList` см. в статье [коллекции](../../mfc/collections.md).  
  
## Пример  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/CPP/clist-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CList`  
  
## Требования  
 **Header:**  afxtempl.h  
  
## См. также  
 [Образец MFC СОБИРАЕТ](../../top/visual-cpp-samples.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)