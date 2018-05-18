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
ms.openlocfilehash: 7ba45c21029a428784e1c8410dcf42295aa6350f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="including-bracketed-filenames"></a>Включение имен файлов в скобках
**ANSI 3.8.2** Метод поиска включаемых файлов исходного кода  
  
 Для спецификаций файлов, заключенных в угловые скобки, препроцессор не ищет каталоги родительских файлов. "Родительский" файл — это файл, содержащий директиву [#include](../preprocessor/hash-include-directive-c-cpp.md). Вместо этого он начинает поиск файла в каталогах, указанных в командной строке компилятора после /I. Если параметр /I не указан или вызывает ошибку, то препроцессор ищет все включаемые файлы, заданные в угловых скобках, в каталогах, которые определены в переменной среды INCLUDE. Переменная среды INCLUDE может содержать несколько путей, разделенных точкой с запятой (**;**). Если параметром /I или переменной среды INCLUDE задано несколько каталогов, то препроцессор просматривает их в том порядке, в котором они указаны.  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)