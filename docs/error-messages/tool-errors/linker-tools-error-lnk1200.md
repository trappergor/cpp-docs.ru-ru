---
title: Ошибка средств компоновщика LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: c99b25a83836f1ee0bc6ba622e42ea382c377172
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466837"
---
# <a name="linker-tools-error-lnk1200"></a>Ошибка средств компоновщика LNK1200

Ошибка при чтении базы данных программы «имя_файла»

Не удалось прочитать базу данных программы (PDB).

Эта ошибка может быть вызвана повреждения файлов.

Если `filename` является PDB-ФАЙЛ для объектного файла, перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).

Если `filename` является PDB-ФАЙЛ для основного выходного файла, и эта ошибка возникает во время инкрементной компоновки, удалите PDB-ФАЙЛ и повторно скомпоновать.