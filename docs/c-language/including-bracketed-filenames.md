---
title: "Включение имен файлов в скобках | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5390e52394005b272e928be396e1e23f5edc72d5
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="including-bracketed-filenames"></a>Включение имен файлов в скобках
**ANSI 3.8.2** Метод поиска включаемых файлов исходного кода  
  
 Для спецификаций файлов, заключенных в угловые скобки, препроцессор не ищет каталоги родительских файлов. "Родительский" файл — это файл, содержащий директиву [#include](../preprocessor/hash-include-directive-c-cpp.md). Вместо этого он начинает поиск файла в каталогах, указанных в командной строке компилятора после /I. Если параметр /I не указан или вызывает ошибку, то препроцессор ищет все включаемые файлы, заданные в угловых скобках, в каталогах, которые определены в переменной среды INCLUDE. Переменная среды INCLUDE может содержать несколько путей, разделенных точкой с запятой (**;**). Если параметром /I или переменной среды INCLUDE задано несколько каталогов, то препроцессор просматривает их в том порядке, в котором они указаны.  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)
