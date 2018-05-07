---
title: -O параметры (оптимизация кода) | Документы Microsoft
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83ddebec9db7a02db40ef31c89c7ff48a66cf665
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="o-options-optimize-code"></a>Параметры /O (оптимизация кода)

**/O** управляют различные оптимизации, которые помогают создавать код для максимально быстрого или минимального размера.

- [/ O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, создающих код минимальный размер.

- [/ O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) задает сочетание оптимизаций, выполняет оптимизацию кода для максимальной скорости.

- [Параметр /OB](../../build/reference/ob-inline-function-expansion.md) управляет подставляемых функций.

- [/Od](../../build/reference/od-disable-debug.md) Отключение оптимизации для ускорения компиляции и упрощения отладки.

- [/Og](../../build/reference/og-global-optimizations.md) включает глобальную оптимизацию.

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) создание встроенных функций для соответствующих вызовов функций.

- [/ OS](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) указывает компилятору предпочитать процессы оптимизации быстродействия размера кода.

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (по умолчанию) указывает компилятору предпочитать процессы оптимизации быстродействия размера кода.

- [/ Ox](../../build/reference/ox-full-optimization.md) — это комбинация вариант, который выбирает некоторые оптимизации, с акцентом на скорость. Он является строгим подмножеством **/O2** оптимизации.

- [/Oy](../../build/reference/oy-frame-pointer-omission.md) отменяет создание указателей на фреймы в стеке вызовов для ускорения вызовов функций.

## <a name="remarks"></a>Примечания

Можно объединять несколько **/o** параметры в отчет один параметр. Например **/Odi** совпадает со значением **/Od /Oi**. Некоторые параметры являются взаимно исключающими и вызывают ошибку компилятора при совместном использовании. В разделе отдельные **/o** параметры для получения дополнительной информации.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)