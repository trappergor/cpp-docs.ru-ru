---
title: Ошибка средств компоновщика LNK1241 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1241
dev_langs:
- C++
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4c11a97dd99515ff7623b77ff31de5fb8577b5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040626"
---
# <a name="linker-tools-error-lnk1241"></a>Ошибка средств компоновщика LNK1241

файл ресурсов «файл ресурсов» уже указан

Эта ошибка возникает в том случае, если вы выполняете **cvtres** вручную из командной строки и затем передать OBJ-файл, полученный файл компоновщику также в других RES-файлы.

Чтобы задать несколько RES-файлов, передавать их компоновщику в виде RES-файлов, не OBJ-файлы созданных с помощью **cvtres**.