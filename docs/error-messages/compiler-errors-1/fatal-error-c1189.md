---
title: "Неустранимая ошибка C1189 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1189
dev_langs: C++
helpviewer_keywords: C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e8d3c9ff44a436688accfe267141390d23c0eb5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1189"></a>Неустранимая ошибка C1189
\#Ошибка: сообщение об ошибке указанное пользователем  
  
 Ошибка C1189 создается `#error` директивы. Разработчик, коды директива задает текст сообщения об ошибке. Дополнительные сведения см. в разделе [(C/C++) директива #error](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 В следующем примере возникает ошибка C1189. В этом примере разработчик задал пользовательское сообщение об ошибке, поскольку `_WIN32` идентификатор не определен:  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Эта ошибка также может появиться при построении проекта ATL с помощью **/ robust** MIDL-параметр компилятора. Используйте **/ robust** коммутатора для построения только [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] и более поздних версиях Windows. Чтобы исправить эту ошибку, используйте один из следующих процедур:  
  
-   Измените эту строку в файле dlldatax.c:  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 на:  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Используйте **Дополнительно** на странице свойств в **MIDL** папка для страниц свойств для удаления **/ robust** переключения, а затем укажите **/no_robust** Неверный параметр. Дополнительные сведения см. в разделе [страницы свойств MIDL: Дополнительно](../../ide/midl-property-pages-advanced.md).  
  
## <a name="see-also"></a>См. также  
 [Директива #define (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)