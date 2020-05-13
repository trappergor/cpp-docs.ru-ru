---
title: Ошибка средств компоновщика LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: d85693cec11ef53a6bbbb60d8ced716d2a0bb131
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754344"
---
# <a name="linker-tools-error-lnk1179"></a>Ошибка средств компоновщика LNK1179

недействительный или поврежденный файл: дубликат «файленое имя» COMDAT

Модуль объекта содержит два или более COMDATs с тем же именем.

Эта ошибка может быть вызвана использованием [/H](../../build/reference/h-restrict-length-of-external-names.md), который ограничивает длину внешних имен, и [/Gy](../../build/reference/gy-enable-function-level-linking.md), который упаковывает функции в COMDATs.

## <a name="example"></a>Пример

В следующем коде, `function1` и `function2` идентичны в первых восьми символов. Компиляция с **/Gy** и **/H8** создает ошибку ссылки.

```cpp
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
