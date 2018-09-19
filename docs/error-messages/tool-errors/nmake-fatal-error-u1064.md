---
title: Неустранимая ошибка NMAKE U1064 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4240bf2c553957e73d5ead0bdd03ea129450645b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093003"
---
# <a name="nmake-fatal-error-u1064"></a>Неустранимая ошибка NMAKE U1064

MAKEFILE не найден и конечный файл не указан

NMAKE командной строки не указан файл makefile или целевой объект и текущий каталог не содержит файл makefile.

NMAKE требует makefile или целевой объект командной строки (или оба). Для предоставления makefile (NMAKE), укажите параметр /F или поместите файл makefile в текущем каталоге. NMAKE можно создать целевой объект командной строки с помощью правило определения, если не указан файл makefile.