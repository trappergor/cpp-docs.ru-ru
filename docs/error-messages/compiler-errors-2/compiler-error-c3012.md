---
title: Ошибка компилятора C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 69f0544815804e9827631be81bf9735a95bd1a22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176706"
---
# <a name="compiler-error-c3012"></a>Ошибка компилятора C3012

> "*внутренний*": встроенная функция не разрешена непосредственно в параллельной области

[Встроенная функция компилятора](../../intrinsics/compiler-intrinsics.md) не может находиться в области `omp parallel` . Чтобы устранить эту проблему, переместите внутренние объекты из региона или замените их невстроенными эквивалентами.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3012 и демонстрирует один из способов его исправления:

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```
