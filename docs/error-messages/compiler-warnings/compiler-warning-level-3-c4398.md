---
title: Предупреждение компилятора (уровень 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 4126a1267b41cdf9c0161c7e85a9057b2a301d77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578468"
---
# <a name="compiler-warning-level-3-c4398"></a>Предупреждение компилятора (уровень 3) C4398

> "*переменной*": глобальный объект для каждого процесса, могут работать неправильно с несколькими доменами приложений; рассмотрите возможность использования __declspec(appdomain)

## <a name="remarks"></a>Примечания

Виртуальная функция с [__clrcall](../../cpp/clrcall.md) соглашение о вызовах в собственном типе вызывает создание в таблице vtable домена приложения. Такой переменной могут некорректно при использовании в нескольких доменах приложений.

Чтобы устранить это предупреждение, явно пометив переменной `__declspec(appdomain)`. В версиях Visual Studio до Visual Studio 2017, чтобы устранить это предупреждение при компиляции с **/CLR: pure**, что делает глобальные переменные для каждого домена приложения по умолчанию. **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

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