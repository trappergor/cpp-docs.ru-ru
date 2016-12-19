---
title: "CMapStringToOb Class | Microsoft Docs"
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
  - "CMapStringToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToOb class"
  - "классы коллекций, string mapping"
  - "строки [C++], class for mapping"
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс коллекции словаря, который сопоставляет уникальным `CString` возражает к указателям `CObject`.  
  
## Синтаксис  
  
```  
class CMapStringToOb : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMapStringToOb::CMapStringToOb](../Topic/CMapStringToOb::CMapStringToOb.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMapStringToOb::GetCount](../Topic/CMapStringToOb::GetCount.md)|Получает число элементов в данном сопоставлении.|  
|[CMapStringToOb::GetHashTableSize](../Topic/CMapStringToOb::GetHashTableSize.md)|Задает текущее количество элементов в хэш\-таблице.|  
|[CMapStringToOb::GetNextAssoc](../Topic/CMapStringToOb::GetNextAssoc.md)|Возвращает следующий элемент для итерации.|  
|[CMapStringToOb::GetSize](../Topic/CMapStringToOb::GetSize.md)|Получает число элементов в данном сопоставлении.|  
|[CMapStringToOb::GetStartPosition](../Topic/CMapStringToOb::GetStartPosition.md)|Возвращает позицию первого элемента.|  
|[CMapStringToOb::HashKey](../Topic/CMapStringToOb::HashKey.md)|Вычисляет хэш\-значение заданного ключа.|  
|[CMapStringToOb::InitHashTable](../Topic/CMapStringToOb::InitHashTable.md)|Инициализирует хэш\-таблицы.|  
|[CMapStringToOb::IsEmpty](../Topic/CMapStringToOb::IsEmpty.md)|Тесты для условия пуст\- сопоставления \(без элементов\).|  
|[CMapStringToOb::Lookup](../Topic/CMapStringToOb::Lookup.md)|Ищет пустой указатель на основе пустом ключе индекса.  Значение указателя, не оно указывает на сущность, используемый для сравнения ключей.|  
|[CMapStringToOb::LookupKey](../Topic/CMapStringToOb::LookupKey.md)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Удаляет все элементы из данного сопоставления.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Удаляет элемент, заданный ключом.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Вставляет элемент в сопоставление; заменяет существующий элемент, если соответствующий ключ поиска.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Вставляет элемент в сопоставление — подстановка оператора для `SetAt`.|  
  
## Заметки  
 Как только вводили пару `CString`\-`CObject*` \(элемент\) в сопоставление, можно эффективно извлекать или удаления пары с помощью строки или значение `CString` в качестве ключа.  Кроме того, можно осуществить перебор всех элементов в сопоставлении.  
  
 Переменная типа **POSITION** используется для другого доступа записи из всех изменениях сопоставления.  Можно использовать **POSITION** "вспоминаете" запись и перебора сопоставление.  Можно представить, что эта итерация последовательная значение ключа. нет.  Последовательность полученных элементов непредвиденна.  
  
 `CMapStringToOb` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Каждый элемент сериализации в свою очередь, если сопоставление хранится в архив или с перегруженным оператора insert \(**\<\<**\) или функцией\-членом `Serialize`.  
  
 Если требуется диагностический дамп отдельных элементов в сопоставлении \(значение `CString` и содержимое `CObject` \), необходимо задать глубину контекст дампа значение 1 или больше.  
  
 Если объект `CMapStringToOb` удаления или при его элементы удалены, удалены объекты `CString` и указатели `CObject`.  Не уничтожены объекты, на которые ссылается `CObject` указателями.  
  
 Источник класса сопоставления похож на вывод списка.  См. статью [коллекции](../../mfc/collections.md) для иллюстрации вывода одноцелевого класса списка.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapStringToOb`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr Class](../Topic/CMapStringToPtr%20Class.md)   
 [CMapStringToString Class](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb Class](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)