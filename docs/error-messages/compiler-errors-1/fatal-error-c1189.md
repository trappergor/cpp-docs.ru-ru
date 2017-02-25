---
title: "Неустранимая ошибка C1189 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1189"
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Неустранимая ошибка C1189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#error: сообщение об ошибке, указанное пользователем  
  
 Ошибка C1189 создается директивой `#error`.  Разработчик, добавляющий в код эту директиву, задает текст сообщения об ошибке.  Для получения дополнительной информации см. [Директива \#error](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 В следующем примере продемонстрировано возникновение ошибки C1189.  В этом примере разработчик задал пользовательское сообщение об ошибке, поскольку идентификатор `_WIN32` не определен.  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Эта ошибка также возникает при построении проекта ATL с помощью параметра **\/robust** компилятора MIDL.  Используйте параметр **\/robust** для построения только [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] и более поздних версиях Windows.  Чтобы устранить эту ошибку, используйте одну из следующих процедур:  
  
-   Измените следующую строку в файле dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 на:  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Воспользуйтесь страницей свойств **Дополнительно** в папке страниц свойств **MIDL**, чтобы удалить параметр **\/robust**, а затем укажите параметр **\/no\_robust**.  Для получения дополнительной информации см. [Страницы свойств MIDL: Дополнительно](../../ide/midl-property-pages-advanced.md).  
  
## См. также  
 [Директива \#define](../../preprocessor/hash-define-directive-c-cpp.md)