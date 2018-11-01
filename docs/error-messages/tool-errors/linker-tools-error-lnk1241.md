---
title: Ошибка средств компоновщика LNK1241
ms.date: 11/04/2016
f1_keywords:
- LNK1241
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
ms.openlocfilehash: 87f73680d7ed40b9b2db9f40f9140976d552ab6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584552"
---
# <a name="linker-tools-error-lnk1241"></a>Ошибка средств компоновщика LNK1241

файл ресурсов «файл ресурсов» уже указан

Эта ошибка возникает в том случае, если вы выполняете **cvtres** вручную из командной строки и затем передать OBJ-файл, полученный файл компоновщику также в других RES-файлы.

Чтобы задать несколько RES-файлов, передавать их компоновщику в виде RES-файлов, не OBJ-файлы созданных с помощью **cvtres**.