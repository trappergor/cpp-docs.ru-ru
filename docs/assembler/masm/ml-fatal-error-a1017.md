---
title: Неустранимая ошибка ML A1017 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: fb98eab68da417526a75beaa57870ce906c85a8d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688563"
---
# <a name="ml-fatal-error-a1017"></a>Неустранимая ошибка ML A1017

**отсутствие исходного имени файла**

Машинного Обучения не удалось найти файл сборки или передать в компоновщик.

Эта ошибка возникает в том случае, когда вы предоставляете параметры командной строки машинного Обучения без указания имени файла, с которым выполняется действие. Чтобы собрать файлы, у которых нет .asm расширение, используйте **/Ta** параметр командной строки.

Эта ошибка может возникнуть путем вызова машинного Обучения без параметров, если ML-переменная среды содержит параметры командной строки.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>