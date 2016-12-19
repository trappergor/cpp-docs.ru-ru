---
title: "Класс CW2CWEX | Microsoft Docs"
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
  - "CW2CWEX"
  - "ATL::CW2CWEX"
  - "ATL.CW2CWEX"
  - "ATL.CW2CWEX<t_nBufferLength>"
  - "ATL::CW2CWEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2CWEX - класс"
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CW2CWEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CW2CTEX` и `CT2CWEX` преобразования строки и typedef `CW2W`.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2CWEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2CWEX::CW2CWEX](../Topic/CW2CWEX::CW2CWEX.md)|Конструктор.|  
|[CW2CWEX::~CW2CWEX](../Topic/CW2CWEX::~CW2CWEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2CWEX::operator LPCWSTR](../Topic/CW2CWEX::operator%20LPCWSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2CWEX::m\_psz](../Topic/CW2CWEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
  
## Заметки  
 Если требуется, используйте `CW2CTEX` дополнительную функциональность, `CT2CWEX` или `CW2W` в коде.  
  
 Этот класс является безопасным для использования в циклах и не переполнит стек.  По умолчанию классы преобразования библиотеки ATL и макросы, используют кодовую страницу ANSI текущую потока для преобразования.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CW2CTEX`  
  
-   `CT2CWEX`  
  
 Следующее определение типа на основе этого класса.  
  
-   `CW2W`  
  
 Обсуждение этих макросов преобразования текста см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Пример  
 См. раздел [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) пример использования этих макросов преобразования строки.  
  
## Требования  
 **Header:** atlconv.h  
  
## См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)