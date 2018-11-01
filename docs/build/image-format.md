---
title: Формат образа
ms.date: 11/04/2016
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
ms.openlocfilehash: 71456af35960114ab64b076ebb9c0f9102613744
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509945"
---
# <a name="image-format"></a>Формат образа

Исполняемый образ имеет PE32 +. Исполняемые образы (DLL или exe) ограничены максимальным размером 2 гигабайта, поэтому относительный адресация с 32-разрядное смещение можно использовать для решения данных статическое изображение. Эти данные включают таблицы адресов импорта, строковые константы, глобальные статические данные и т. д.

## <a name="see-also"></a>См. также

[Программные соглашения для X64](../build/x64-software-conventions.md)