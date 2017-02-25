---
title: "CMapPtrToPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapPtrToPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapPtrToPtr class"
  - "классы коллекций, pointer mapping"
  - "pointer mapping class"
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMapPtrToPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обозреватель сопоставлении пустых указателей, ключом которых является пустым указателями.  
  
## Синтаксис  
  
```  
class CMapPtrToPtr : public CObject  
```  
  
## Члены  
 Функции\-члены `CMapPtrToPtr` похожи на функции\-членам класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  Сходство вследствие этого, можно использовать документации `CMapStringToOb` для особенностях функции\-члена.  Везде, где можно увидеть указатель `CObject` в качестве параметра или возвращаемого значения функции замените указатель на `void`.  Везде, где можно увидеть `CString` или указатель **const** к `char` в качестве параметра или возвращаемого значения функции замените указатель на `void`.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 например, преобразуется в  
  
 `BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`  
  
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
 `CMapPtrToPtr` содержит макрос `IMPLEMENT_DYNAMIC` для поддержки доступа типа во время выполнения и сбрасывать на `CDumpContext` объект.  Если требуется дамп отдельных элементов карты \(значения указателя\), необходимо задать глубину контекст дампа значение 1 или больше.  
  
 Сопоставления Указатель\-к\-указателя не могут быть сериализованы.  
  
 Если объект `CMapPtrToPtr` удаления или при его элементы удалены указатели, а не только удалены сущности, на который они ссылаются.  
  
 Дополнительные сведения о `CMapPtrToPtr` см. в статье [коллекции](../../mfc/collections.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMapPtrToPtr`  
  
## Требования  
 **Header:**  afxcoll.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)