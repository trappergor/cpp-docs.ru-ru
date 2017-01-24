---
title: "Класс CA2AEX | Microsoft Docs"
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
  - "ATL::CA2AEX<t_nBufferLength>"
  - "CA2AEX"
  - "ATL.CA2AEX<t_nBufferLength>"
  - "ATLCONV/CA2AEX"
  - "ATL.CA2AEX"
  - "ATL::CA2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2AEX - класс"
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CA2AEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CA2TEX` и `CT2AEX` преобразования строки и typedef **CA2A**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2AEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2AEX::CA2AEX](../Topic/CA2AEX::CA2AEX.md)|Конструктор.|  
|[CA2AEX::~CA2AEX](../Topic/CA2AEX::~CA2AEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2AEX::operator LPSTR](../Topic/CA2AEX::operator%20LPSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2AEX::m\_psz](../Topic/CA2AEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
|[CA2AEX::m\_szBuffer](../Topic/CA2AEX::m_szBuffer.md)|Статический буфер, используемый для хранения преобразованная строка.|  
  
## Заметки  
 Если требуется, используйте `CA2TEX` дополнительную функциональность, `CT2AEX` или **CA2A** в собственном коде.  
  
 Этот класс содержит буфер фиксированного размера статический, который используется для хранения результата преобразования.  Если результат слишком велик, чтобы поместить в буфер статический класс выделяет память с помощью `malloc`, освобождая память, если объект выходит из области.  Это гарантирует, что, в отличие от макросы преобразования текста, доступные в предыдущих версиях библиотеки ATL этот класс является безопасным для использования в циклах и что он не переполнит стек.  
  
 Если класс пытается выделить память в куче и происходит сбой, то он будет вызывать `AtlThrow` с аргументом **E\_OUTOFMEMORY**.  
  
 По умолчанию классы преобразования библиотеки ATL и макросы, используют кодовую страницу ANSI текущую потока для преобразования.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CA2TEX`  
  
-   `CT2AEX`  
  
 Следующее определение типа на основе этого класса.  
  
-   **CA2A**  
  
 Обсуждение этих макросов преобразования текста см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Пример  
 См. раздел [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) пример использования этих макросов преобразования строки.  
  
## Требования  
 **Header:** atlconv.h  
  
## См. также  
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)