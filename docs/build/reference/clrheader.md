---
title: "-CLRHEADER | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /CLRHEADER
dev_langs: C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 699fa0e97236b1c5cf207e73dcbb39156bfbb130
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>Примечания  
 где:  
  
 `file`  
 Файл изображения созданного с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="remarks"></a>Примечания  
 CLRHEADER отображает сведения о заголовках .NET, используемых в любом управляемом приложении. Выходные данные показывают расположение и размер в байтах заголовка .NET и разделов в заголовке.  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
 Когда параметр/CLRHEADER применяется для файла, который был скомпилирован с параметром/CLR, будет **заголовка clr:** раздела dumpbin выходные данные.  Значение **флаги** указывает, использовалась/CLR-параметр:  
  
-   0 — / CLR (образ может содержать машинный код).  
  
-   1 — / CLR: safe (образ содержит код MSIL, только работать на любой платформе CLR и возможно, поддается проверке).  
  
-   3 — / CLR: pure (образ содержит только код MSIL, но может работать на x86 только платформы).  
  
 Программным путем можно проверить, если изображение было создано для среды CLR.  Дополнительные сведения см. в разделе [как: определить, является ли изображение машинный код или CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 Параметры компилятора **/CLR: pure** и **/CLR: safe** в Visual Studio 2015 не рекомендуется использовать.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)