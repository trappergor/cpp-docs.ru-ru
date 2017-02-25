---
title: "CStrBufT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStrBufT<TCharType>"
  - "ATL.CStrBufT"
  - "CStrBufT"
  - "ATL::CStrBufT"
  - "ATL.CStrBufT<TCharType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStrBufT class"
  - "shared classes, CStrBufT"
  - "строки [C++], custom memory management"
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CStrBufT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет автоматическую очистку ресурсов для `GetBuffer` и вызовы `ReleaseBuffer` на существующем `CStringT` объект.  
  
## Синтаксис  
  
```  
  
      template<  
   typename TCharType  
>  
class CStrBufT  
```  
  
#### Параметры  
 *TCharType*  
 Символьный тип класса `CStrBufT`.  Может принимать следующие значения:  
  
-   `char` \(для символьных строк ANSI\)  
  
-   `wchar_t` \(для символьных строк в юникоде\)  
  
-   **TCHAR** \(и для символьных строк ANSI и Юникода\)  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|`PCXSTR`|Указатель на постоянной строки.|  
|`PXSTR`|Указатель на строку.|  
|`StringType`|Строковый тип буфера которого необходимо манипулированным специализациями этого шаблона класса.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStrBufT::CStrBufT](../Topic/CStrBufT::CStrBufT.md)|Конструктор объекта буфера строки.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStrBufT::SetLength](../Topic/CStrBufT::SetLength.md)|Устанавливает длину буфера знаков связанного объекта строки.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStrBufT::operator PCXSTR](../Topic/CStrBufT::operator%20PCXSTR.md)|Извлекает указатель на буфер символов **const** связанного объекта строки.|  
|[CStrBufT::operator PXSTR](../Topic/CStrBufT::operator%20PXSTR.md)|Извлекает указатель на буфер символов связанного объекта строки.|  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[CStrBufT::AUTO\_LENGTH](../Topic/CStrBufT::AUTO_LENGTH.md)|Автоматически определяет новую длину строки в выпуске.|  
|[CStrBufT::SET\_LENGTH](../Topic/CStrBufT::SET_LENGTH.md)|Задайте длину строкового объекта во время GetBuffer|  
  
## Заметки  
 Этот класс используется класс\-оболочка, как заменить вызовы [GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) и [ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md) или [GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md) и `ReleaseBuffer`.  
  
 В основном, предназначенный как вспомогательный класс, `CStrBufT` предоставляет удобный способ для разработчиков работать с буфером символа строкового объекта, не задумываясь о том, как `ReleaseBuffer` или после вызова.  Это возможно, поскольку объект программы\-оболочки выходит из области обычно в случае исключения или выйти из нескольких ветвей кода; вызывать его деструктор освободить ресурс строки.  
  
## Требования  
 **Header:** atlsimpstr.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)