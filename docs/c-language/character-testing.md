---
title: Тестирование символов
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: 31a90f28d710ffc1b58f9c6b3fcfd01fd8d2d00c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523205"
---
# <a name="character-testing"></a>Тестирование символов

**ANSI 4.3.1** Наборы символов, тестируемые функциями `isalnum`, `isalpha`, `iscntrl`, `islower`, `isprint` и `isupper`

В следующей таблице приведено описание этих функций в соответствии с реализацией компилятором Microsoft C.

|Функция|Тестируемые наборы символов|
|--------------|---------------|
|`isalnum`|Символы 0–9, A–Z, a–z (коды ASCII 48–57, 65–90, 97–122)|
|`isalpha`|Символы A–Z, a–z (коды ASCII 65–90, 97–122)|
|`iscntrl`|Коды ASCII 0–31, 127|
|`islower`|Символы a–z (коды ASCII 97–122)|
|`isprint`|Символы A–Z, a–z, 0–9, пунктуация, пробел (коды ASCII 32–126)|
|`isupper`|Символы A–Z (коды ASCII 65–90)|

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)