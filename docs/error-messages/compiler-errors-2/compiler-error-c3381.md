---
title: Ошибка компилятора C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: ae416d68831d1964c89d938dfcddd364e521195c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328868"
---
# <a name="compiler-error-c3381"></a>Ошибка компилятора C3381

«сборка»: спецификаторы доступа к сборке доступны только в коде, скомпилированном с параметром/CLR

Собственные типы могут быть отображены за пределами сборки, но можно указать только доступ к сборке для собственных типов в **/CLR** компиляции.

Дополнительные сведения см. в разделе [введите видимость](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3381.

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```