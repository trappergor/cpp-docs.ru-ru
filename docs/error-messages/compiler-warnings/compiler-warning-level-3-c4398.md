---
title: Предупреждение (уровень 3) C4398 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c38ade6b75242fdd5144481e3415e914cb6773c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704618"
---
# <a name="compiler-warning-level-3-c4398"></a>Предупреждение компилятора (уровень 3) C4398

> "*переменной*": глобальный объект для каждого процесса может работать неправильно с несколькими доменами приложений; рассмотрите возможность использования __declspec(appdomain)

## <a name="remarks"></a>Примечания

Виртуальная функция с [__clrcall](../../cpp/clrcall.md) соглашение о вызовах в машинный тип вызывает создание в vtable домена приложения. Такой переменной могут некорректно при использовании в нескольких доменах приложений.

Чтобы устранить это предупреждение явным созданием переменной `__declspec(appdomain)`. В версиях Visual Studio до Visual Studio 2017 г., чтобы устранить это предупреждение при компиляции с **/CLR: pure**, что делает глобальные переменные для каждого домена приложения по умолчанию. **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

Дополнительные сведения см. в разделе [appdomain](../../cpp/appdomain.md) и [домены приложений и Visual C++](../../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4398.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```