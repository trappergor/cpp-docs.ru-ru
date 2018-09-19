---
title: Предупреждение компилятора (уровень 1) C4678 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81eb7df618f97300c2654cc0f4f7a58d18215b26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076103"
---
# <a name="compiler-warning-level-1-c4678"></a>Предупреждение компилятора (уровень 1) C4678

базовый класс "базовый_тип" менее доступен, чем "производный_тип"

Открытый тип является производным от закрытого типа. Если экземпляр открытого типа создается в связанной сборке, то члены закрытого базового типа будут недоступны.

Предупреждение C4678 возникает только недоступна при использовании параметра компилятора устаревшие **/CLR: oldSyntax**. Является ошибкой при использовании **/CLR**, наличие базового класса, менее доступного, производный от него класс.
