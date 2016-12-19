---
title: "Класс CW2AEX | Microsoft Docs"
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
  - "ATL::CW2AEX<t_nBufferLength>"
  - "CW2AEX"
  - "ATL.CW2AEX<t_nBufferLength>"
  - "ATL::CW2AEX"
  - "ATL.CW2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2AEX - класс"
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CW2AEX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется макросами `CT2AEX`, `CW2TEX`, `CW2CTEX` и `CT2CAEX` и typedef **CW2A** преобразования строки.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2AEX  
```  
  
#### Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода.  По умолчанию длина составляет 128 байт.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2AEX::CW2AEX](../Topic/CW2AEX::CW2AEX.md)|Конструктор.|  
|[CW2AEX::~CW2AEX](../Topic/CW2AEX::~CW2AEX.md)|Деструктор.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2AEX::operator LPSTR](../Topic/CW2AEX::operator%20LPSTR.md)|Оператор преобразования.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CW2AEX::m\_psz](../Topic/CW2AEX::m_psz.md)|Элемент данных, в котором хранится строка источника.|  
|[CW2AEX::m\_szBuffer](../Topic/CW2AEX::m_szBuffer.md)|Статический буфер, используемый для хранения преобразованная строка.|  
  
## Заметки  
 Если требуется, используйте `CT2AEX` дополнительную функциональность, `CW2TEX`, `CW2CTEX`, `CT2CAEX` или **CW2A** в коде.  
  
 Этот класс содержит буфер фиксированного размера статический, который используется для хранения результата преобразования.  Если результат слишком велик, чтобы поместить в буфер статический класс выделяет память с помощью `malloc`, освобождая память, если объект выходит из области.  Это гарантирует, что, в отличие от макросы преобразования текста, доступные в предыдущих версиях библиотеки ATL этот класс является безопасным для использования в циклах и что он не переполнит стек.  
  
 Если класс пытается выделить память в куче и происходит сбой, то он будет вызывать `AtlThrow` с аргументом **E\_OUTOFMEMORY**.  
  
 По умолчанию классы преобразования библиотеки ATL и макросы, используют кодовую страницу ANSI текущую потока для преобразования.  Если необходимо переопределить этой функциональности для определенного преобразования, укажите кодовую страницу в качестве второго параметра в конструктор класса.  
  
 Следующие макросы основаны на этом классе.  
  
-   `CT2AEX`  
  
-   `CW2TEX`  
  
-   `CW2CTEX`  
  
-   `CT2CAEX`  
  
 Следующее определение типа на основе этого класса.  
  
-   **CW2A**  
  
 Обсуждение этих макросов преобразования текста см. в разделе [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Пример  
 См. раздел [Макросы преобразования строки библиотеки ATL и MFC](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) пример использования этих макросов преобразования строки.  
  
## Требования  
 **Header:** atlconv.h  
  
## См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)