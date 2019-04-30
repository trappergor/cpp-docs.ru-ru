---
title: Ошибка средств компоновщика LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299060"
---
# <a name="linker-tools-error-lnk2017"></a>Ошибка средств компоновщика LNK2017

Перемещение «symbol», «сегмент» будет неправильной без: No

Вы пытаетесь создать 64-разрядный образ с 32-разрядными адресами. Чтобы сделать это, необходимо сделать следующее:

- Используйте фиксированный адрес загрузки.

- Ограничьте размер изображения до 3 ГБ.

- Укажите [: no](../../build/reference/largeaddressaware-handle-large-addresses.md).