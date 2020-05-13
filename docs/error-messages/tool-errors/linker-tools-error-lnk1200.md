---
title: Ошибка средств компоновщика LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: 9dcc37bd74a25e29726529346b1578bb8b18ac3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195140"
---
# <a name="linker-tools-error-lnk1200"></a>Ошибка средств компоновщика LNK1200

Ошибка при чтении базы данных программы "имяфайла"

Не удалось прочитать базу данных программы (PDB).

Эта ошибка может быть вызвана повреждением файла.

Если `filename` является PDB для объектного файла, перескомпилируйте объектный файл с помощью [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).

Если `filename` является PDB для основного выходного файла и эта ошибка произошла во время добавочной компоновки, удалите PDB-файл и перекомпоновку.
