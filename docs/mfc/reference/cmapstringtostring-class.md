---
title: "CMapStringToString Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapStringToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToString class"
  - "классы коллекций, string mapping"
  - "строки [C++], class for mapping"
  - "строки [C++], сопоставление"
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMapStringToString Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сопоставления `CString` обозреватель объектов, ключом которых является `CString` объект.  
  
## Синтаксис  
  
```  
class CMapStringToString : public CObject  
```  
  
## Члены  
 Функции\-члены `CMapStringToString` похожи на функции\-членам класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  Сходство вследствие этого, можно использовать документации `CMapStringToOb` для особенностях функции\-члена.  Везде, где можно увидеть указатель `CObject` в качестве параметра или возвращаемого значения функции "вывода" замените указатель на `char`.  Везде, где можно увидеть указатель `CObject` в качестве параметра функции "ввода", замените указатель на `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 например, преобразуется в  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### Открытые структуры  
  
|Имя|Описание|  
|---------|--------------|  
|[CMapStringToString::CPair](../Topic/CMapStringToString::CPair.md)|Вложенная структура, содержащая значение ключа и значение связанного объекта строки.|  
  
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
|[CMapStringToString::PGetFirstAssoc](../Topic/CMapStringToString::PGetFirstAssoc.md)|Получает указатель на первый `CString` в сопоставлении.|  
|[CMapStringToString::PGetNextAssoc](../Topic/CMapStringToString::PGetNextAssoc.md)|Получает указатель на следующий `CString` для итерации.|  
|[CMapStringToString::PLookup](../Topic/CMapStringToString::PLookup.md)|Возвращает указатель на `CString` значение которого соответствует заданному значению.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Удаляет все элементы из данного сопоставления.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Удаляет элемент, заданный ключом.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Вставляет элемент в сопоставление; заменяет существующий элемент, если соответствующий ключ поиска.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Вставляет элемент в сопоставление — подстановка оператора для `SetAt`.|  
  
## Заметки  
 `CMapStringToString` содержит макрос `IMPLEMENT_SERIAL` для поддержки сериализации и сбрасывать его элементов.  Каждый элемент сериализации в свою очередь, если сопоставление хранится в архив или с перегруженным оператора insert \(**\<\<**\) или функцией\-членом `Serialize`.  
  
 Если требуется дамп отдельного `CString`\- элементов `CString`, необходимо установить глубину контекста дампа значение 1 или больше.  
  
 Если объект `CMapStringToString` удаления или при его элементы удалены объекты `CString` удалены как подходит.  
  
 Дополнительные сведения о `CMapStringToString` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapStringToString`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [Образец MFC СОБИРАЕТ](../../top/visual-cpp-samples.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)