---
title: Ошибка средств компоновщика LNK2017 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80af2bb6475fc37b7feba5b29bfe9c1292740286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022454"
---
# <a name="linker-tools-error-lnk2017"></a>Ошибка средств компоновщика LNK2017

Перемещение «symbol», «сегмент» будет неправильной без: No

Вы пытаетесь создать 64-разрядный образ с 32-разрядными адресами. Чтобы сделать это, необходимо сделать следующее:

- Используйте фиксированный адрес загрузки.

- Ограничьте размер изображения до 3 ГБ.

- Укажите [: no](../../build/reference/largeaddressaware-handle-large-addresses.md).