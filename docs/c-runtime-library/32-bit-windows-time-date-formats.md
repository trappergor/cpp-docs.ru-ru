---
title: Форматы даты и времени в 32-разрядных операционных системах Windows | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- vc.time
dev_langs:
- C++
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55eca447de7818f749628505a4c4f2fa6eb0dcd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061120"
---
# <a name="32-bit-windows-timedate-formats"></a>Форматы даты и времени в 32-разрядных операционных системах Windows

Дата и время изменения файла хранятся отдельно в виде битовых полей с использованием целых чисел без знака. Дата и время изменения файла упаковываются следующим образом:

### <a name="time"></a>Время

|Позиция разряда:|0   1   2   3   4|5   6   7   8   9   A|B   C   D   E   F|
|-------------------|-----------------------|---------------------------|-----------------------|
|Длина:|5|6|5|
|Содержимое:|часы|минуты|С шагом 2 секунды|
|Диапазон значений:|0-23|0-59|0–29 с шагом 2 секунды|

### <a name="date"></a>дата.

|Позиция разряда:|0   1   2   3   4   5   6|7   8   9   A|B   C   D   E   F|
|-------------------|-------------------------------|-------------------|-----------------------|
|Длина:|7|4|5|
|Содержимое:|год|месяц|дн|
|Диапазон значений:|0–119|1–12|1–31|
||(относительно 1980)|||

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)