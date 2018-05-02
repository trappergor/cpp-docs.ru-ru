---
title: Неустранимая ошибка ML A1017 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1017
dev_langs:
- C++
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5fcb2d921a40b35c6022b2aca1e22adc2d8c45e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-fatal-error-a1017"></a>Неустранимая ошибка ML A1017
**отсутствие исходного имени файла**  
  
 ML не удалось найти файл для сборки или передать в компоновщик.  
  
 Эта ошибка возникает, когда вы предоставляете ML параметры командной строки без указания имени файла, с которым выполняется действие. Чтобы собрать файлы, которые не имеют расширение .asm, используйте **/Ta** параметр командной строки.  
  
 Эта ошибка также может возникать путем вызова машинного Обучения без параметров, если переменная среды ML содержит параметры командной строки.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)