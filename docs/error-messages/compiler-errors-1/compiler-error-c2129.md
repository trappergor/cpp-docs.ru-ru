---
title: Ошибка компилятора C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: e55107419235420d272c738e9d8ef7cf277c11c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593466"
---
# <a name="compiler-error-c2129"></a>Ошибка компилятора C2129

Статическая функция «функция» объявлена, но не определена

Прямая ссылка при попытке `static` функция, которая не определена.

Объект `static` функция должна быть определена в области файла. Если функция определена в другом файле, он должен быть объявлен `extern`.