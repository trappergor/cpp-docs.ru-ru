---
title: "CFixedStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFixedStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class"
  - "shared classes, CFixedStringT"
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CFixedStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет объект строки с фиксированным буфером знака.  
  
## Синтаксис  
  
```  
  
      template< class   
      StringType  
      , int   
      t_nChars  
       >    
class CFixedStringT : private CFixedStringMgr, public StringType  
```  
  
#### Параметры  
 `StringType`  
 Используется как базовый класс для фиксированного строкового объекта и может принимать любое `CStringT`\- на тип.  Некоторые примеры включают `CString`, `CStringA` и `CStringW`.  
  
 *t\_nChars*  
 Число знаков, хранимых в буфере.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFixedStringT::CFixedStringT](../Topic/CFixedStringT::CFixedStringT.md)|Конструктор для строкового объекта.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFixedStringT::operator \=](../Topic/CFixedStringT::operator%20=.md)|Присвоить новое значение объекта `CFixedStringT`.|  
  
## Заметки  
 Этот класс пример пользовательского класса строки на основе `CStringT`.  Хотя подобный, а 2 класса отличаются в реализации.  Основные различия между `CFixedStringT` и `CStringT`:  
  
-   Начальный буфере символов выделения как часть объекта и имеет *t\_nChars* размера.  Это позволяет объекту **CFixedString**, чтобы занимать непрерывный блок памяти для целей производительности.  Однако если содержимое объекта `CFixedStringT` растут за *t\_nChars*, буфер выборки.  
  
-   Буфер знака для объекта `CFixedStringT` всегда имеют одинаковую длину \(*t\_nChars*\).  Отсутствие ограничений на размер буфера для объектов `CStringT`.  
  
-   Диспетчер памяти для `CFixedStringT` настраивать тем, что совместное использование объекта между двумя или более [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) не разрешено objectsis `CFixedStringT`.  Объекты `CStringT` не имеющие это ограничение.  
  
 Дополнительные сведения о настройке `CFixedStringT` и управлении памятью для строкового объекта см. в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## Иерархия наследования  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## Требования  
 **Header:** cstringt.h  
  
## См. также  
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)