---
title: "CMapWordToOb Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapWordToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapWordToOb class"
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMapWordToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обозреватель указателей `CObject` сопоставление ключевых слов 16\-разрядных.  
  
## Синтаксис  
  
```  
class CMapWordToOb : public CObject  
```  
  
## Члены  
 Функции\-члены `CMapWordToOb` похожи на функции\-членам класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  Сходство вследствие этого, можно использовать документации `CMapStringToOb` для особенностях функции\-члена.  Везде, где можно увидеть `CString` или указатель **const** к `char` в качестве параметра или возвращаемого значения функции заместительское **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 например, преобразуется в  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Каждый элемент сериализации в свою очередь, если сопоставление хранится в архив или с перегруженным оператора insert \(**\<\<**\) или функцией\-членом `Serialize`.  
  
 Если требуется дамп отдельного **WORD**\- элементов `CObject`, необходимо установить глубину контекста дампа значение 1 или больше.  
  
 Если объект `CMapWordToOb` удаления или при его элементы удалены, указателей `CObject` удалены.  Не уничтожены объекты, на которые ссылается `CObject` указателями.  
  
 Дополнительные сведения о `CMapWordToOb` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapWordToOb`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)