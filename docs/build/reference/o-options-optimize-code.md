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
ms.openlocfilehash: ffd3023120f1d930a24ccef6fa297594062322df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320426"
---
# <a name="o-options-optimize-code"></a>Параметры /O (оптимизация кода)

**/O** параметры управляют различные оптимизации, которые помогут вам создать код для максимальной скорости или минимальный размер.

- [/ O1](o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, создающих код минимальный размер.

- [/ O2](o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, оптимизация кода для максимальной скорости.

- [/OB](ob-inline-function-expansion.md) управляет подставляемых функций.

- [/Od](od-disable-debug.md) отключает оптимизацию для ускорения компиляции и упрощения отладки.

- [/Og](og-global-optimizations.md) включает глобальную оптимизацию.

- [/Oi](oi-generate-intrinsic-functions.md) создание встроенных функций для соответствующих вызовов функций.

- [/OS](os-ot-favor-small-code-favor-fast-code.md) указывает компилятору предпочитать оптимизации для скорости размера кода.

- [/Ot](os-ot-favor-small-code-favor-fast-code.md) (по умолчанию) указывает компилятору предпочитать оптимизации для скорости и размера кода.

- [/Ox](ox-full-optimization.md) — это сочетание вариант, который выбирает несколько оптимизаций с акцентом на скорость. Это является строгим подмножеством **/O2** оптимизации.

- [/Oy](oy-frame-pointer-omission.md) отменяет создание указателей фрейма в стеке вызовов для ускорения вызовов функций.

## <a name="remarks"></a>Примечания

Можно объединить несколько **/O** параметры в отдельный параметр оператор. Например **/Odi** совпадает со значением **/Od /Oi**. Некоторые параметры являются взаимоисключающими и вызывает ошибку компилятора, если используются вместе. См. в разделе отдельные **/O** параметров.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
