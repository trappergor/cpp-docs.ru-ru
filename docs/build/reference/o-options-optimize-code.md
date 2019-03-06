---
title: Параметры /O (оптимизация кода)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: d884da19936949f2feeb96cb1fb88057d5dcd948
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419703"
---
# <a name="o-options-optimize-code"></a>Параметры /O (оптимизация кода)

**/O** параметры управляют различные оптимизации, которые помогут вам создать код для максимальной скорости или минимальный размер.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, создающих код минимальный размер.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, оптимизация кода для максимальной скорости.

- [/OB](../../build/reference/ob-inline-function-expansion.md) управляет подставляемых функций.

- [/Od](../../build/reference/od-disable-debug.md) отключает оптимизацию для ускорения компиляции и упрощения отладки.

- [/Og](../../build/reference/og-global-optimizations.md) включает глобальную оптимизацию.

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) создание встроенных функций для соответствующих вызовов функций.

- [/OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) указывает компилятору предпочитать оптимизации для скорости размера кода.

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (по умолчанию) указывает компилятору предпочитать оптимизации для скорости и размера кода.

- [/Ox](../../build/reference/ox-full-optimization.md) — это сочетание вариант, который выбирает несколько оптимизаций с акцентом на скорость. Это является строгим подмножеством **/O2** оптимизации.

- [/Oy](../../build/reference/oy-frame-pointer-omission.md) отменяет создание указателей фрейма в стеке вызовов для ускорения вызовов функций.

## <a name="remarks"></a>Примечания

Можно объединить несколько **/O** параметры в отдельный параметр оператор. Например **/Odi** совпадает со значением **/Od /Oi**. Некоторые параметры являются взаимоисключающими и вызывает ошибку компилятора, если используются вместе. См. в разделе отдельные **/O** параметров.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
