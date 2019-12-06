---
title: Неустранимая ошибка ML A1017
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 6fb0835cca135fc994866dc2453734d7b3012a64
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856830"
---
# <a name="ml-fatal-error-a1017"></a>Неустранимая ошибка ML A1017

**отсутствует имя исходного файла**

МАШИНному обучению не удалось найти файл для сборки или передачи в компоновщик.

Эта ошибка возникает при предоставлении параметров командной строки ML без указания имени файла для действия. Чтобы собрать файлы, не имеющие расширения ASM, используйте параметр командной строки **/та** .

Эту ошибку также можно создать, вызвав ML без параметров, если переменная среды машинного обучения содержит параметры командной строки.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>