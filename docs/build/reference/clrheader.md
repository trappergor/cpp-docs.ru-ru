---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: e35cf79cdaa10c9632e1c588e2b49f45cfbef283
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330857"
---
# <a name="clrheader"></a>/CLRHEADER

Отобразить сведения, относящиеся к среде CLR.

## <a name="syntax"></a>Синтаксис

> / CLRHEADER *файла*

### <a name="arguments"></a>Аргументы

*file*<br/>
Файл изображения построены [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Примечания

**/ CLRHEADER** отображает сведения о заголовках .NET, используемых в любом управляемом приложении. Выходные данные расположение и размер в байтах, заголовка .NET и разделов в заголовке.

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

При **/CLRHEADER** используется в файле, который был скомпилирован с параметром/CLR, будет существовать **clr заголовка:** раздел в выходных данных (программа DUMPBIN). Значение **флаги** указывает, использовалась параметра/clr:

- 0 — / CLR (образ может содержать машинный код).

Можно также программным путем проверять, если образ был создан для среда CLR.  Дополнительные сведения см. в разделе [как: определить, является ли изображение машинный код или среда CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017. Код, который должен быть «чистым» или «безопасных» должна быть перенесена в C#.

## <a name="see-also"></a>См. также

- [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)
