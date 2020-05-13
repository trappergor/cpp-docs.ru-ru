---
title: Неустранимая ошибка C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: 83135b77ceb75b4c2b05211260d1aed8fac6777f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320303"
---
# <a name="fatal-error-c1060"></a>Неустранимая ошибка C1060

компилятору не хватает размера кучи

Операционная система или библиотека времени выполнения не могут выполнить запрос на предоставление памяти.

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Чтобы устранить эту проблему, попробуйте следующие возможные решения

1. Если компилятор также выдает ошибки [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) и [C3859,](../../error-messages/compiler-errors-2/compiler-error-c3859.md)используйте опцию компилятора [/M,](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) чтобы снизить лимит распределения памяти. Если уменьшить распределение оставшейся памяти, в куче останется больше места для вашего приложения.

   Если опция [/Зм](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) уже установлена, попробуйте удалить его. Место в куче может быть исчерпано из-за того, что предел распределения памяти, заданный с помощью этого параметра, слишком велик. Компилятор использует лимит по умолчанию, если вы удалите опцию [/ ММ.](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)

1. Если компиляция происходит на 64-разрядной платформе, используйте 64-разрядный набор средств компиляции. Для получения информации [см. Как: Включить 64-битный визуальный набор c ' на командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).

1. На 32-битной Windows попробуйте использовать [/3GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) коммутатор boot.ini.

1. Увеличьте размер файла подкачки Windows.

1. Закройте все запущенные программы.

1. Удалите неиспользуемые включенные файлы.

1. Удалите ненужные глобальные переменные, например, путем динамического распределения памяти вместо объявления крупного массива.

1. Удалите неиспользуемые объявления.

1. Разделите данный файл на меньшие файлы.
