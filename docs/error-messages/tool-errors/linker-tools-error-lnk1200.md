---
title: Ошибка средств компоновщика LNK1200 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1200
dev_langs:
- C++
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ecd51142bf30230b6b177a36e007345e93bf2c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059320"
---
# <a name="linker-tools-error-lnk1200"></a>Ошибка средств компоновщика LNK1200

Ошибка при чтении базы данных программы «имя_файла»

Не удалось прочитать базу данных программы (PDB).

Эта ошибка может быть вызвана повреждения файлов.

Если `filename` является PDB-ФАЙЛ для объектного файла, перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).

Если `filename` является PDB-ФАЙЛ для основного выходного файла, и эта ошибка возникает во время инкрементной компоновки, удалите PDB-ФАЙЛ и повторно скомпоновать.