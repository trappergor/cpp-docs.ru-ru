---
title: Ошибка компилятора ресурсов RC2148 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2148
dev_langs:
- C++
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b78bf8e9eb9ebe86dae75856ea3c0b6f5d34a26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075913"
---
# <a name="resource-compiler-error-rc2148"></a>Ошибка компилятора ресурсов RC2148

ID ДИАЛЕКТЕ, слишком велик

Значение идентификатора варианта языка вне допустимого диапазона.

Оператор **LANGUAGE** должен использовать следующий синтаксис:

**LANGUAGE** *ИД_основного_языка*,*ИД_дополнительного_языка*

Допустимые идентификаторы варианта языка, определяются как **SUBLANG_** константы в файле WINNT.h.