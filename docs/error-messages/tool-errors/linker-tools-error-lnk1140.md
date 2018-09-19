---
title: Ошибка средств компоновщика LNK1140 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f850360bc749a41e548cebae9f58f9fc7d3d420
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044708"
---
# <a name="linker-tools-error-lnk1140"></a>Ошибка средств компоновщика LNK1140

слишком много модулей для базы данных программы; связь с параметром/PDB: NONE

Проект содержит больше 4096 модулей.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Выполнить повторную компоновку с помощью [/PDB: NONE](../../build/reference/pdb-use-program-database.md).

1. Скомпилируйте некоторые модули без отладочной информации.

1. Уменьшите количество модулей.