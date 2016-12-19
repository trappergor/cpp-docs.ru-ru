---
title: "Класс CA2WEX | Microsoft Docs"
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
  - "ATLCONV/CA2WEX"
  - "ATL.CA2WEX"
  - "ATL.CA2WEX<t_nBufferLength>"
  - "ATL::CA2WEX"
  - "ATL::CA2WEX<t_nBufferLength>"
  - "CA2WEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2WEX - класс"
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CA2WEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CA2TEX`, `CA2CTEX`, `CT2WEX` и `CT2CWEX` и typedef **CA2W** преобразования строки.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2WEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2WEX::CA2WEX](../Topic/CA2WEX::CA2WEX.md)|Конструктор.|  
|[CA2WEX::~CA2WEX](../Topic/CA2WEX::~CA2WEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2WEX::operator LPWSTR](../Topic/CA2WEX::operator%20LPWSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CA2WEX::m\_psz](../Topic/CA2WEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
|[CA2WEX::m\_szBuffer](../Topic/CA2WEX::m_szBuffer.md)|Статический буфер, используемый для хранения преобразованная строка.|  
  
## Заметки  
 Если требуется, используйте `CA2TEX` дополнительную функциональность, `CA2CTEX`, `CT2WEX`, `CT2CWEX` или **CA2W** в коде.  
  
 Этот класс содержит буфер фиксированного размера статический, который используется для хранения результата преобразования.  Если результат слишком велик, чтобы поместить в буфер статический класс выделяет память с помощью `malloc`, освобождая память, если объект выходит из области.  Это гарантирует, что, в отличие от макросы преобразования текста, доступные в предыдущих версиях библиотеки ATL этот класс является безопасным для использования в циклах и что он не переполнит стек.  
  
 Если класс пытается выделить память в куче и происходит сбой, то он будет вызывать `AtlThrow` с аргументом **E\_OUTOFMEMORY**.  
  
 По умолчанию классы преобразования библиотеки ATL и макросы, используют кодовую страницу ANSI текущую потока для преобразования.  Если необходимо переопределить этой функциональности для определенного преобразования, укажите кодовую страницу в качестве второго параметра в конструктор класса.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CA2TEX`  
  
-   `CA2CTEX`  
  
-   `CT2WEX`  
  
-   `CT2CWEX`  
  
 Следующее определение типа на основе этого класса.  
  
-   **CA2W**  
  
 Обсуждение этих макросов преобразования текста см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Пример  
 См. раздел [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) пример использования этих макросов преобразования строки.  
  
## Требования  
 **Header:** atlconv.h  
  
## См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)