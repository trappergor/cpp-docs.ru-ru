---
title: "-CLRHEADER | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73f68c4f73d132254ea64d4b3b3b9f787f3a4b82
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 `file`  
 Файл изображения созданного с помощью [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="remarks"></a>Примечания  
 CLRHEADER отображает сведения о заголовках .NET, используемых в любом управляемом приложении. Выходные данные показывают расположение и размер в байтах заголовка .NET и разделов в заголовке.  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
 Когда параметр/CLRHEADER применяется для файла, который был скомпилирован с параметром/CLR, будет **заголовка clr:** раздела dumpbin выходные данные.  Значение **флаги** указывает, использовалась/CLR-параметр:  
  
-   0 — / CLR (образ может содержать машинный код).  
  
 Программным путем можно проверить, если изображение было создано для среды CLR.  Дополнительные сведения см. в разделе [как: определить, является ли изображение машинный код или CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и будет удален в будущей версии компилятора. Код, который должен быть «чистые» или «безопасной» должна быть перенесена в C#. 
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)