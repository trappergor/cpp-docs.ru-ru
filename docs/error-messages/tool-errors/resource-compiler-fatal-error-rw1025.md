---
title: Неустранимая ошибка компилятора ресурсов RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 8ecfc11f5cc991294d966a4b6c75d8da6669d5b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575686"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Неустранимая ошибка компилятора ресурсов RW1025

Не хватает памяти дальней кучи

Проверьте наличие программного обеспечения оперативной памяти, которое могут занимать слишком много места. Используйте программу CHKDSK, чтобы узнать, какой объем памяти, у вас есть.

Если вы создаете ресурс большого объема, разделить файл скрипта ресурсов на два файла. После создания двух RES-файлов, используйте командную строку MS-DOS для их соединения:

```
copy first.res /b + second.res /b full.res
```