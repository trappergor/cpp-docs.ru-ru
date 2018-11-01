---
title: Неустранимая ошибка NMAKE U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: 71213391032989e5faf8889761b29194928125a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463366"
---
# <a name="nmake-fatal-error-u1064"></a>Неустранимая ошибка NMAKE U1064

MAKEFILE не найден и конечный файл не указан

NMAKE командной строки не указан файл makefile или целевой объект и текущий каталог не содержит файл makefile.

NMAKE требует makefile или целевой объект командной строки (или оба). Для предоставления makefile (NMAKE), укажите параметр /F или поместите файл makefile в текущем каталоге. NMAKE можно создать целевой объект командной строки с помощью правило определения, если не указан файл makefile.