---
title: Включение имен файлов в кавычках
ms.date: 11/04/2016
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
ms.openlocfilehash: 4083519d6f6b9b4d037b0c2998737f3a5062c6cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232960"
---
# <a name="including-quoted-filenames"></a>Включение имен файлов в кавычках

**ANSI 3.8.2** Поддержка заключенных в кавычки имен для включаемых файлов исходного кода

Если указана полная и неоднозначная спецификация пути для включаемого файла между двумя наборами двойных кавычек (" "), препроцессор ищет только спецификацию пути и игнорирует стандартные каталоги.

Для включаемых файлов, заданных в виде [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", поиск по каталогам начинается с каталога родительского файла и продолжается по каталогам всех прародительских файлов. Таким образом, поиск начинается относительно каталога, который содержит обрабатываемый в настоящее время файл исходного кода. Если отсутствует файл "прародителя" и файл не найден, поиск продолжается, как если бы имя файла было включено в угловые скобки.

## <a name="see-also"></a>См. также

[Директивы предварительной обработки](../c-language/preprocessing-directives.md)
