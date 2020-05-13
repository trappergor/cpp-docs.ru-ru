---
title: Предупреждение средств компоновщика LNK4070
ms.date: 11/04/2016
f1_keywords:
- LNK4070
helpviewer_keywords:
- LNK4070
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
ms.openlocfilehash: 391a477625b51fd37eacc5d455801ce90d2abbc2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194009"
---
# <a name="linker-tools-warning-lnk4070"></a>Предупреждение средств компоновщика LNK4070

/OUT: filename директива в. EXP отличается от выходного имени файла "имяфайла"; пропуск директивы

`filename`, указанные в инструкции [Name](../../build/reference/name-c-cpp.md) или [Library](../../build/reference/library.md) , когда файл. exp был создан, отличается от выходного `filename`, который был либо принят по умолчанию, либо указан с помощью параметра [/out](../../build/reference/out-output-file-name.md) .

Это предупреждение появляется при изменении имени выходного файла в среде разработки и в том случае, если DEF файла проекта не был обновлен. Обновите файл. def вручную, чтобы устранить это предупреждение.

Клиентская программа, использующая полученную библиотеку DLL, может столкнуться с проблемами.
