---
title: Предупреждение компилятора (уровень 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: d33e5c60bac657060ffef2a43686a5f737eb11cc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161312"
---
# <a name="compiler-warning-level-4-c4212"></a>Предупреждение компилятора (уровень 4) C4212

использовано нестандартное расширение: в объявлении функции используется многоточие

Прототип функции имеет переменное число аргументов. Определение функции не имеет значение.

Следующий пример приводит к возникновению ошибки C4212:

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```
