---
title: "-O параметры (оптимизация кода) | Документы Microsoft"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs: C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7da04384d0c4ea00c2eaaedbcf0ec770e216289
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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