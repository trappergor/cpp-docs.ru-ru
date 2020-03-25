---
title: Ошибка средств компоновщика LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: 00041e677ac7b69df9981551ee3b6cc18f9eb33d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183765"
---
# <a name="linker-tools-error-lnk1264"></a>Ошибка средств компоновщика LNK1264

Указан параметр/LTCG: PGINSTRUMENT, но создание кода не требуется; Сбой инструментирования

Указан параметр **/LTCG: PGINSTRUMENT** , но не найдены OBJ-файлы, скомпилированные с помощью [/GL](../../build/reference/gl-whole-program-optimization.md). Невозможно выполнить инструментирование, так как произошел сбой связи. В командной строке должен быть хотя бы один OBJ-файл, скомпилированный с параметром **/GL** , чтобы можно было выполнить инструментирование.

Профильная оптимизация (PGO) доступна только в 64-разрядных компиляторах.
