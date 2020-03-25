---
title: Ошибка средств компоновщика LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: 02e80de5c34809a331003f3b0fb28d32e138a531
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194737"
---
# <a name="linker-tools-error-lnk2017"></a>Ошибка средств компоновщика LNK2017

перемещение символа в "сегмент" недопустимо без/LARGEADDRESSAWARE: нет

Вы пытаетесь создать 64-разрядный образ с 32-битным адресом. Для этого необходимо выполнить следующие действия.

- Используйте фиксированный адрес загрузки.

- Ограничьте образ до 3 ГБ.

- Укажите [/LARGEADDRESSAWARE: No](../../build/reference/largeaddressaware-handle-large-addresses.md).
