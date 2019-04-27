---
title: Ошибка средств компоновщика LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 48c735f29918c4d1caeb15123f7376276d116fb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255070"
---
# <a name="linker-tools-error-lnk1140"></a>Ошибка средств компоновщика LNK1140

слишком много модулей для базы данных программы; связь с параметром/PDB: NONE

Проект содержит больше 4096 модулей.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Выполнить повторную компоновку с помощью [/PDB: NONE](../../build/reference/pdb-use-program-database.md).

1. Скомпилируйте некоторые модули без отладочной информации.

1. Уменьшите количество модулей.