---
title: "Класс CA2CAEX | Microsoft Docs"
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
  - "ATL.CA2CAEX"
  - "ATL.CA2CAEX<t_nBufferLength>"
  - "ATLCONV/CA2CAEX"
  - "ATL::CA2CAEX<t_nBufferLength>"
  - "ATL::CA2CAEX"
  - "CA2CAEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2CAEX - класс"
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CA2CAEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CA2CTEX` и `CT2CAEX` преобразования строки и typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2CAEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2CAEX::CA2CAEX](../Topic/CA2CAEX::CA2CAEX.md)|Конструктор.|  
|[CA2CAEX::~CA2CAEX](../Topic/CA2CAEX::~CA2CAEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2CAEX::operator LPCSTR](../Topic/CA2CAEX::operator%20LPCSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2CAEX::m\_psz](../Topic/CA2CAEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
  
## Заметки  
 Если требуется, используйте `CA2CTEX` дополнительную функциональность, `CT2CAEX` или **CA2CA** в собственном коде.  
  
 Этот класс является безопасным для использования в циклах и не переполнит стек.  По умолчанию классы преобразования библиотеки ATL и макросы, будут использовать кодовую страницу ANSI текущую потока для преобразования.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CA2CTEX`  
  
-   `CT2CAEX`  
  
 Следующее определение типа на основе этого класса.  
  
-   **CA2CA**  
  
 Обсуждение этих макросов преобразования текста см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Пример  
 См. раздел [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) пример использования этих макросов преобразования строки.  
  
## Требования  
 **Header:** atlconv.h  
  
## См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)