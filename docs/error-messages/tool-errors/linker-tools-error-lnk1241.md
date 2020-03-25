---
title: Ошибка средств компоновщика LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: 6e2b955787166c94be4ca35e1c58df5becd243f2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183817"
---
# <a name="linker-tools-error-lnk1241"></a>Ошибка средств компоновщика LNK1241

файл ресурсов "файл ресурсов" уже указан

Эта ошибка возникает при запуске **CVTRES** вручную из командной строки и при передаче результирующего OBJ-файла компоновщику в дополнение к другим RES-файлам.

Чтобы указать несколько RES-файлов, передайте их в компоновщик как RES-файлы, а не в OBJ-файлы, созданные с помощью **CVTRES**.
