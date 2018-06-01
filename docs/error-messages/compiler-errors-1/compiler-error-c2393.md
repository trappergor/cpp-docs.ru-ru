---
title: Ошибка компилятора C2393 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 057537c8efcf6e827d9ac9aaf36c0eace6d24156
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704034"
---
# <a name="compiler-error-c2393"></a>Ошибка компилятора C2393

> "*символ*": символ по доменам приложения не может быть помещен в сегмент "*сегмент*"

## <a name="remarks"></a>Примечания

**/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

Использование [appdomain](../../cpp/appdomain.md) переменных подразумевает, что компиляция выполняется с **/CLR: pure** или **/CLR: safe**, и безопасный или чистый образ не может содержать сегменты данных.

В разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) для получения дополнительной информации.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2393. Чтобы устранить эту проблему, не создавайте сегмента данных.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```