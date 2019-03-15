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
ms.openlocfilehash: 6a1240e2d3ad2ac3a454c610a6f49d07e50951e5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820706"
---
# <a name="clrheader"></a>/CLRHEADER

Отобразить сведения, относящиеся к среде CLR.

## <a name="syntax"></a>Синтаксис

> / CLRHEADER *файла*

### <a name="arguments"></a>Аргументы

*file*<br/>
Файл изображения построены [/CLR](clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Примечания

**/ CLRHEADER** отображает сведения о заголовках .NET, используемых в любом управляемом приложении. Выходные данные расположение и размер в байтах, заголовка .NET и разделов в заголовке.

Только [/Headers](headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](gl-whole-program-optimization.md) параметр компилятора.

При **/CLRHEADER** используется в файле, который был скомпилирован с параметром/CLR, будет существовать **clr заголовка:** раздел в выходных данных (программа DUMPBIN). Значение **флаги** указывает, использовалась параметра/clr:

- 0 — / CLR (образ может содержать машинный код).

Можно также программным путем проверять, если образ был создан для среда CLR.  Дополнительные сведения см. в разделе [Как Определить, является ли изображение машинный код или среда CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

**/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017. Код, который должен быть «чистым» или «безопасных» должна быть перенесена в C#.

## <a name="see-also"></a>См. также

- [Параметры DUMPBIN](dumpbin-options.md)
