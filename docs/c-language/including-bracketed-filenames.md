---
title: Включение имен файлов в скобках | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37b4d0e6ccf0c0c01671082d2596528632fba6cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100868"
---
# <a name="including-bracketed-filenames"></a>Включение имен файлов в скобках

**ANSI 3.8.2** Метод поиска включаемых файлов исходного кода

Для спецификаций файлов, заключенных в угловые скобки, препроцессор не ищет каталоги родительских файлов. "Родительский" файл — это файл, содержащий директиву [#include](../preprocessor/hash-include-directive-c-cpp.md). Вместо этого он начинает поиск файла в каталогах, указанных в командной строке компилятора после /I. Если параметр /I не указан или вызывает ошибку, то препроцессор ищет все включаемые файлы, заданные в угловых скобках, в каталогах, которые определены в переменной среды INCLUDE. Переменная среды INCLUDE может содержать несколько путей, разделенных точкой с запятой (**;**). Если параметром /I или переменной среды INCLUDE задано несколько каталогов, то препроцессор просматривает их в том порядке, в котором они указаны.

## <a name="see-also"></a>См. также

[Директивы предварительной обработки](../c-language/preprocessing-directives.md)