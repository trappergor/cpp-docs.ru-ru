---
title: -CLRHEADER | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5896e12d5e3b3b3984884388d11c6380e900d73d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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