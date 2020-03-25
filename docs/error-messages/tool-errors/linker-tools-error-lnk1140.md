---
title: Ошибка средств компоновщика LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 845c796ee9611e921e2fd1707b9bb956ab62a5ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195270"
---
# <a name="linker-tools-error-lnk1140"></a>Ошибка средств компоновщика LNK1140

слишком много модулей для базы данных программы; связать с параметром/PDB: NONE

Проект содержит более 4096 модулей.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Выполните повторную компоновку с помощью [/pdb: None](../../build/reference/pdb-use-program-database.md).

1. Скомпилируйте некоторые модули без отладочной информации.

1. Сократите число модулей.
