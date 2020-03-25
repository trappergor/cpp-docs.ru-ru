---
title: Неустранимая ошибка C1107
ms.date: 11/04/2016
f1_keywords:
- C1107
helpviewer_keywords:
- C1107
ms.assetid: 541a4d9f-10bc-4dd8-b68e-15e548f3dc0a
ms.openlocfilehash: 6e8df232b4d3f3b18eb7c37bcc418ca030a93aef
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203792"
---
# <a name="fatal-error-c1107"></a>Неустранимая ошибка C1107

не удалось найти сборку "файл": укажите путь поиска сборок с помощью переключателя/AI или переменной среды LIBPATH

Файл метаданных был передан в директиву [#using](../../preprocessor/hash-using-directive-cpp.md) , которую компилятору не удалось разместить.

Переменная среды LIBPATH, описанная в разделе `#using`, и параметр компилятора [/AI](../../build/reference/ai-specify-metadata-directories.md) позволяют указать каталоги, в которых компилятор будет искать файлы метаданных, на которые имеются ссылки.
