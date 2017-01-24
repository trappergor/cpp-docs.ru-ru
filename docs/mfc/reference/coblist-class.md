---
title: "CObList Class | Microsoft Docs"
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
  - "CObList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObList class"
  - "списки, объект"
  - "объекты [C++], lists of"
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Поддерживает упорядоченные списки неуникального указателей, доступных `CObject` последовательно или значением указателя.  
  
## Синтаксис  
  
```  
class CObList : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObList::CObList](../Topic/CObList::CObList.md)|Создает пустой список для указателей `CObject`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CObList::AddHead](../Topic/CObList::AddHead.md)|Добавляет элемент \(или все элементы в других список\) в начало списка \(делает новую головку\).|  
|[CObList::AddTail](../Topic/CObList::AddTail.md)|Добавляет элемент \(или все элементы в других список\) в кабелю списка \(делает новый хвост\).|  
|[CObList::Find](../Topic/CObList::Find.md)|Получает положение элемента, заданного значением указателя.|  
|[CObList::FindIndex](../Topic/CObList::FindIndex.md)|Получает положение элемента, указанного на нулевой\- индексу.|  
|[CObList::GetAt](../Topic/CObList::GetAt.md)|Возвращает элемент на заданной позиции.|  
|[CObList::GetCount](../Topic/CObList::GetCount.md)|Получает число элементов в данном списке.|  
|[CObList::GetHead](../Topic/CObList::GetHead.md)|Возвращает головной элемент списка \(не может быть пустым\).|  
|[CObList::GetHeadPosition](../Topic/CObList::GetHeadPosition.md)|Возвращает позицию головного элемента списка.|  
|[CObList::GetNext](../Topic/CObList::GetNext.md)|Возвращает следующий элемент для итерации.|  
|[CObList::GetPrev](../Topic/CObList::GetPrev.md)|Возвращает предыдущий элемент для итерации.|  
|[CObList::GetSize](../Topic/CObList::GetSize.md)|Получает число элементов в данном списке.|  
|[CObList::GetTail](../Topic/CObList::GetTail.md)|Возвращает элемент списка с префиксом tail \(не может быть пустым\).|  
|[CObList::GetTailPosition](../Topic/CObList::GetTailPosition.md)|Возвращает позицию элемента с префиксом tail списка.|  
|[CObList::InsertAfter](../Topic/CObList::InsertAfter.md)|Вставляет новый элемент после заданной позиции.|  
|[CObList::InsertBefore](../Topic/CObList::InsertBefore.md)|Вставляет новый элемент до заданной позиции.|  
|[CObList::IsEmpty](../Topic/CObList::IsEmpty.md)|Тесты для пустого состояния списка \(без элементов\).|  
|[CObList::RemoveAll](../Topic/CObList::RemoveAll.md)|Удаляет все элементы из этого списка.|  
|[CObList::RemoveAt](../Topic/CObList::RemoveAt.md)|Удаляет элемент из этого списка, указанного по позиции.|  
|[CObList::RemoveHead](../Topic/CObList::RemoveHead.md)|Удаляет элемент из списка head.|  
|[CObList::RemoveTail](../Topic/CObList::RemoveTail.md)|Удаляет элемент из списка с префиксом tail.|  
|[CObList::SetAt](../Topic/CObList::SetAt.md)|Задает элемент по заданной позиции.|  
  
## Заметки  
 Списки `CObList` аналогично поведению двойной\- связанные списки.  
  
 Переменная типа **POSITION** ключ для списка.  Можно использовать переменную **POSITION** и в виде итератора для просмотра списка последовательно и как закладка, чтобы сохранить место.  Позиция не то же, что и индекс.  
  
 Вставка элемента очень быстро в начало списка на кабеле и в известном **POSITION**.  Последовательный поиск необходим для поиска элемента по значению или по индексу.  Этот поиск может быть медленным, если список длинный.  
  
 `CObList` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Если список указателей `CObject` хранится в архив или с перегруженным оператора insert или функцией\-членом `Serialize`, то каждый элемент `CObject` сериализации в свою очередь.  
  
 Если требуется дамп отдельных элементов `CObject` в списке, необходимо установить глубину контекста дампа значение 1 или больше.  
  
 Если объект `CObList` удаления или при его элементы удалены только указатели `CObject`, а не объекты удалены они ссылаются.  
  
 Можно создать собственные классы из `CObList`.  Новый класс списка, предназначенный для хранения указателей на объекты, производным от `CObject` добавляет новые элементы данных и новых функций\-членов.  Обратите внимание, что результирующий список не является строго safe типа, потому что он допускает вставку любого указателя `CObject`.  
  
> [!NOTE]
>  Необходимо использовать макрос [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) в реализации производного класса, если планируется выполнить сериализацию списка.  
  
 Дополнительные сведения об использовании `CObList` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CObList`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CStringList Class](../Topic/CStringList%20Class.md)   
 [CPtrList Class](../Topic/CPtrList%20Class.md)