---
title: /CLRHEADER
ms.date: 05/16/2019
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: 5974606448dad103c8f12a126b8d17c688927c88
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837165"
---
# <a name="clrheader"></a>/CLRHEADER

Отображение сведений о среде CLR.

## <a name="syntax"></a>Синтаксис

> /CLRHEADER *файл*

### <a name="arguments"></a>Аргументы

*file*<br/>
Файл образа, сборка которого выполняется с параметром [/clr](clr-common-language-runtime-compilation.md).

## <a name="remarks"></a>Примечания

Параметр **/CLRHEADER** выводит сведения о заголовках .NET, используемых в любой управляемой программе. В выходных данных указываются расположение и размер в байтах заголовка .NET и его разделов.

С файлами, созданными с использованием параметра компилятора [/GL](gl-whole-program-optimization.md), можно использовать только параметр DUMPBIN [/HEADERS](headers.md).

Если с файлом, скомпилированным с параметром /clr, используется параметр **/CLRHEADER**, в выходных данных dumpbin будет раздел **clr Header:** . Значение **flags** указывает, какой параметр /clr использовался:

- 0 -- /clr (образ может содержать машинный код).

Проверить, была ли сборка образа выполнена для общеязыковой среды выполнения, можно также программными средствами.  Дополнительные сведения см. в разделе [Практическое руководство. Машинный код или среда CLR: определение цели созданного образа](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).

Параметры компилятора **/clr:pure** и **/clr:safe** не рекомендуется использовать в Visual Studio 2015, и они не поддерживаются в Visual Studio 2017 и более поздних версий. Код, который должен быть "чистым" или "безопасным", необходимо портировать на C#.

## <a name="see-also"></a>См. также

- [Параметры DUMPBIN](dumpbin-options.md)
