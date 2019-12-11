---
title: Ошибка средств компоновщика LNK1256
ms.date: 11/04/2016
f1_keywords:
- LNK1256
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
ms.openlocfilehash: bedf96262944d59737a39a942021cdec9445f3b8
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990943"
---
# <a name="linker-tools-error-lnk1256"></a>Ошибка средств компоновщика LNK1256

Ошибка операции ALINK : причина

Наиболее частая причина LNK1256 — неверный номер версии сборки. Значение 65535 не может быть использовано в любой части номера версии сборки. Допустимый диапазон версий сборки — 0-65534.

LNK1256 может возникнуть в случае, если ALINK не удается найти именованный контейнер ключа. Удалите контейнер ключей и снова добавьте его в CSP строгого имени с помощью [программы Sn. exe (средство строгих имен)](/dotnet/framework/tools/sn-exe-strong-name-tool).

Еще одна возможная причина ошибки LNK1256 — несовпадение версий компоновщика и Alink.dll. Это может быть вызвано поврежденной установкой Visual Studio. Используйте **программы и компоненты** на панели управления Windows для восстановления или переустановки Visual Studio.

Следующий пример приводит к возникновению ошибки LNK1256:

```cpp
// LNK1256.cpp
// compile with: /clr /LD
// LNK1256 expected
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];
public class CMyClass {
public:
   int value;
};
```
