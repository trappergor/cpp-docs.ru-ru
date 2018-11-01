---
title: Неустранимая ошибка C1107
ms.date: 11/04/2016
f1_keywords:
- C1107
helpviewer_keywords:
- C1107
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
ms.openlocfilehash: 135e8da1b49eb1d86f6186e8683ced2f5152a3a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484822"
---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107

не удалось найти сборку «файл»: укажите путь поиска сборок с помощью переключателя /AI или переменной среды LIBPATH

Файл метаданных был передан [#using](../../preprocessor/hash-using-directive-cpp.md) директивы, компилятору не удалось найти.

LIBPATH, который описан в разделе, посвященном `#using`и [/AI](../../build/reference/ai-specify-metadata-directories.md) параметр компилятора позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на который указывает ссылка.