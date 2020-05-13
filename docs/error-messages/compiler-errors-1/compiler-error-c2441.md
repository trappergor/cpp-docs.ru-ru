---
title: Ошибка компилятора C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: 4e5d5335717ec77c61069ad08e209f9e1851dc2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205313"
---
# <a name="compiler-error-c2441"></a>Ошибка компилятора C2441

> "*переменная*": символ, объявленный с __declspec (Process), должен быть константой в режиме/clr: pure

## <a name="remarks"></a>Remarks

Параметры компилятора **/clr: pure** и **/clr: Сейф** являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

По умолчанию переменные задаются для каждого домена приложения в **параметре/CLR: pure**. Переменная, помеченная `__declspec(process)` в **параметре/CLR: pure** , подвержена ошибкам, если изменена в одном домене приложения и прочитана в другом.

Таким образом, компилятор принудительно применяет переменные для каждого процесса `const` в **параметре/CLR: pure**, делая их только для чтения во всех доменах приложений.

Дополнительные сведения см. в разделе [Process](../../cpp/process.md) и [/CLR (компиляция общеязыковой среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2441.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```
