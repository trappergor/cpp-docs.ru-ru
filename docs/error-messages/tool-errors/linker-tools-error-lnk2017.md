---
title: Ошибка средств компоновщика LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641472"
---
# <a name="linker-tools-error-lnk2017"></a>Ошибка средств компоновщика LNK2017

Перемещение «symbol», «сегмент» будет неправильной без: No

Вы пытаетесь создать 64-разрядный образ с 32-разрядными адресами. Чтобы сделать это, необходимо сделать следующее:

- Используйте фиксированный адрес загрузки.

- Ограничьте размер изображения до 3 ГБ.

- Укажите [: no](../../build/reference/largeaddressaware-handle-large-addresses.md).