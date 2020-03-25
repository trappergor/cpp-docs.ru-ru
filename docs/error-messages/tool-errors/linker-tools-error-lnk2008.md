---
title: Ошибка средств компоновщика LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: c7794d09f7eeb9dceba7098ca7af90ccf2eeccad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194828"
---
# <a name="linker-tools-error-lnk2008"></a>Ошибка средств компоновщика LNK2008

Целевой объект адресной привязки не согласован "symbol_name"

Ссылка обнаружила в объектном файле цель адресной привязки, которая не была правильно согласована.

Эта ошибка может быть вызвана настраиваемым выравниванием сектон (например, #pragma [Pack](../../preprocessor/pack.md)), модификатором [выравнивания](../../cpp/align-cpp.md) или кодом на языке ассемблера, который изменяет выравнивание сектон.

Если в коде не используется ни один из указанных выше элементов, это может быть вызвано компилятором.
