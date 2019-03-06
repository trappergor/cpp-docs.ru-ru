---
title: Быстрая компиляция
ms.date: 11/04/2016
helpviewer_keywords:
- performance, cle.exe compiler
- compilation, performance
- cl.exe compiler, performance
- fast compiling
ms.assetid: 5fead136-ba69-40c8-8e25-236f89d5990a
ms.openlocfilehash: e613e12eb9089348ea3f82bc5fac43d569a89f35
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426164"
---
# <a name="fast-compilation"></a>Быстрая компиляция

Для увеличения скорости компиляции:

- Используйте [минимальное перестроение](../../build/reference/gm-enable-minimal-rebuild.md), в которой компилятор C++ повторно компилирует исходный файл только в том случае, если он зависит от изменения класса в файле заголовка.

- [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md) и использовать [предкомпилированный заголовок параметры](../../build/reference/yc-create-precompiled-header-file.md).

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
