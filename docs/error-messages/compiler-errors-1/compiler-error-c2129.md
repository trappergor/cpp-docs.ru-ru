---
title: Ошибка компилятора C2129 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2129
dev_langs:
- C++
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e86515a7d7c8954271578291c4ebcb1a52fc9863
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054289"
---
# <a name="compiler-error-c2129"></a>Ошибка компилятора C2129

Статическая функция «функция» объявлена, но не определена

Прямая ссылка при попытке `static` функция, которая не определена.

Объект `static` функция должна быть определена в области файла. Если функция определена в другом файле, он должен быть объявлен `extern`.