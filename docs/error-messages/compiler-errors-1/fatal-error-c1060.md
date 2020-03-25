---
title: Неустранимая ошибка C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: f1a7c3ccab716a9281d4520f4c5fce2afff60187
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204442"
---
# <a name="fatal-error-c1060"></a>Неустранимая ошибка C1060

компилятору не хватает размера кучи

Операционная система или библиотека времени выполнения не могут выполнить запрос на предоставление памяти.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Чтобы устранить эту проблему, попробуйте следующие возможные решения

1. Если компилятор также выдает ошибки [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) и [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), используйте параметр компилятора [/ZM](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) , чтобы уменьшить ограничение на выделение памяти. Если уменьшить распределение оставшейся памяти, в куче останется больше места для вашего приложения.

   Если параметр [/ZM](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) уже задан, попробуйте удалить его. Место в куче может быть исчерпано из-за того, что предел распределения памяти, заданный с помощью этого параметра, слишком велик. Если удалить параметр [/ZM](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) , компилятор использует ограничение по умолчанию.

1. Если компиляция происходит на 64-разрядной платформе, используйте 64-разрядный набор средств компиляции. Дополнительные сведения см. в разделе [как включить 64-разрядный визуальный C++ набор инструментов в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. В 32-разрядной версии Windows попробуйте использовать параметр [/3gb](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) Boot. ini.

1. Увеличьте размер файла подкачки Windows.

1. Закройте все запущенные программы.

1. Удалите неиспользуемые включенные файлы.

1. Удалите ненужные глобальные переменные, например, путем динамического распределения памяти вместо объявления крупного массива.

1. Удалите неиспользуемые объявления.

9. Разделите данный файл на меньшие файлы.
