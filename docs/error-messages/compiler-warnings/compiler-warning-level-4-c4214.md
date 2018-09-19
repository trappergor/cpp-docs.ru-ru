---
title: Предупреждение компилятора (уровень 4) C4214 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4214
dev_langs:
- C++
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 879c959bfe851b56dbc60b4eeb714db8d7f9dfaf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027431"
---
# <a name="compiler-warning-level-4-c4214"></a>Предупреждение компилятора (уровень 4) C4214

использовано нестандартное расширение: типы битовых полей, отличные от int

В расширениях Майкрософт по умолчанию (/Ze) члены битового поля структуры может быть любой целочисленный тип.

## <a name="example"></a>Пример

```
// C4214.c
// compile with: /W4
struct bitfields
{
   unsigned short j:4;  // C4214
};

int main()
{
}
```

Такие битовые поля недопустимы в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).