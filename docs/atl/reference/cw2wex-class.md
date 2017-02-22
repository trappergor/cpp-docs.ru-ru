---
title: "Класс CW2WEX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CW2WEX"
  - "ATL.CW2WEX<t_nBufferLength>"
  - "ATL::CW2WEX"
  - "ATL.CW2WEX"
  - "ATL::CW2WEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2WEX - класс"
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс CW2WEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CW2TEX` и `CT2WEX` преобразования строки и typedef `CW2W`.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2WEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2WEX::CW2WEX](../Topic/CW2WEX::CW2WEX.md)|Конструктор.|  
|[CW2WEX::~CW2WEX](../Topic/CW2WEX::~CW2WEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2WEX::operator LPWSTR](../Topic/CW2WEX::operator%20LPWSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2WEX::m\_psz](../Topic/CW2WEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
|[CW2WEX::m\_szBuffer](../Topic/CW2WEX::m_szBuffer.md)|Статический буфер, используемый для хранения преобразованная строка.|  
  
## Заметки  
 Если требуется, используйте `CW2TEX` дополнительную функциональность, `CT2WEX` или `CW2W` в коде.  
  
 Этот класс содержит буфер фиксированного размера статический, который используется для хранения результата преобразования.  Если результат слишком велик, чтобы поместить в буфер статический класс выделяет память с помощью `malloc`, освобождая память, если объект выходит из области.  Это гарантирует, что, в отличие от макросы преобразования текста, доступные в предыдущих версиях библиотеки ATL этот класс является безопасным для использования в циклах и что он не переполнит стек.  
  
 Если класс пытается выделить память в куче и происходит сбой, то он будет вызывать `AtlThrow` с аргументом **E\_OUTOFMEMORY**.  
  
 По умолчанию классы преобразования библиотеки ATL и макросы, используют кодовую страницу ANSI текущую потока для преобразования.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CW2TEX`  
  
-   `CT2WEX`  
  
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
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)