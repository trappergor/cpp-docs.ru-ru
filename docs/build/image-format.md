---
title: Формат изображения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 356480333a62d998213726016f3940b318c218a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="image-format"></a>Формат образа
Формата исполняемого образа используется PE32 +. Исполняемые образы (DLL или exe) являются ограничивается максимальным размером 2 ГБ, поэтому относительный адресация с 32-разрядное смещение можно использовать для решения данных статическое изображение. Эти данные включают адресную таблицу импорта, строковые константы, статические глобальные данные и т. д.  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)