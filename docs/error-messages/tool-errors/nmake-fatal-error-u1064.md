---
title: Неустранимая ошибка NMAKE U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: bfc42c458c1932287f17f367d09c4b23c2c201a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182829"
---
# <a name="nmake-fatal-error-u1064"></a>Неустранимая ошибка NMAKE U1064

ФАЙЛ MAKEFILE не найден, и не указан целевой объект

В командной строке NMAKE не указан файл makefile или целевой объект, а текущий каталог не содержит файла с именем MAKEFILE.

Для NMAKE требуется либо файл makefile, либо целевой объект командной строки (или оба). Чтобы сделать файл Makefile доступным для NMAKE, укажите параметр/F или поместите в текущий каталог файл с именем MAKEFILE. NMAKE может создать целевой объект командной строки с помощью правила вывода, если файл makefile не предоставлен.
