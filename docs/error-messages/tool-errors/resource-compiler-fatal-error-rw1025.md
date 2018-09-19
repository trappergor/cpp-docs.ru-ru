---
title: Неустранимая ошибка компилятора ресурсов RW1025 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bf7bdeed320c004ffb75fa1d25d9b89147b0c13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117404"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Неустранимая ошибка компилятора ресурсов RW1025

Не хватает памяти дальней кучи

Проверьте наличие программного обеспечения оперативной памяти, которое могут занимать слишком много места. Используйте программу CHKDSK, чтобы узнать, какой объем памяти, у вас есть.

Если вы создаете ресурс большого объема, разделить файл скрипта ресурсов на два файла. После создания двух RES-файлов, используйте командную строку MS-DOS для их соединения:

```
copy first.res /b + second.res /b full.res
```