---
title: Ошибка компилятора ресурсов RC2147 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2147
dev_langs:
- C++
helpviewer_keywords:
- RC2147
ms.assetid: 09974f06-1731-4e70-b373-f9218e0ee8d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f3ca510dfd61e92a33f599c7ef261e03b8ad2cb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032855"
---
# <a name="resource-compiler-error-rc2147"></a>Ошибка компилятора ресурсов RC2147

Идентификатор варианта языка не является числом

Значение идентификатора варианта языка должно быть числом.

Оператор **LANGUAGE** должен использовать следующий синтаксис:

**LANGUAGE** *ИД_основного_языка*,*ИД_дополнительного_языка*

Допустимые идентификаторы варианта языка, определяются как **SUBLANG_** константы в файле WINNT.h.