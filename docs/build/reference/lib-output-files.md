---
title: Выходные LIB-файлы
ms.date: 11/04/2016
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: 8aeb46b0249ddf4155277866f7d8537bbfa98244
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439385"
---
# <a name="lib-output-files"></a>Выходные LIB-файлы

Выходные файлы, создаваемые библиотекой LIB, зависят от режима, в котором они используются, как показано в следующей таблице.

|Режим|Выходные данные|
|----------|------------|
|По умолчанию (сборка или изменение библиотеки)|Библиотека COFF (. lib)|
|Извлечение члена с помощью/EXTRACT|Файл объекта (obj)|
|Создание файла экспорта и импорт библиотеки с помощью/DEF|Импорт библиотеки (lib) и файла экспорта (exp)|

## <a name="see-also"></a>См. также раздел

[Общие сведения о LIB](overview-of-lib.md)
