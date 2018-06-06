---
title: 'Как: перенести - clr: безопасный (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- migration [C++], verifiable assemblies
- upgrading Visual C++ applications, verifiable assemblies
- verifiable assemblies [C++], migrating to
- /clr compiler option [C++], migrating to /clr:safe
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d72be19eb893a74a17a988e8c14c6bdaba766cbc
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704518"
---
# <a name="how-to-migrate-to-clrsafe-ccli"></a>Практическое руководство. Миграция в /clr:safe (C++/CLI)

> [!IMPORTANT]
> **/CLR: pure** и **/CLR: safe** параметры компилятора являются устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г. Если вам требуется безопасно сборки среды CLR, мы рекомендуем перенести код на C#.

При использовании более ранней версии инструментов компилятора Visual C++ из перед 2017 г. Visual Studio может создавать компоненты с помощью **/CLR: safe**, который указывает компилятору на необходимость создания ошибок для каждого не поддающейся конструкция кода.

## <a name="remarks"></a>Примечания

Следующие проблемы создает проверяемости ошибки:

- Собственные типы. Даже если он не используется, объявление собственных классов, структур, указателей или массивов может помешать компиляции.

- Глобальные переменные

- Вызовы функции в неуправляемой библиотеке, включая общие вызовы функций среды выполнения языка

- Проверяемая функция не может содержать [оператор static_cast](../cpp/static-cast-operator.md) для приведения вниз. [Оператор static_cast](../cpp/static-cast-operator.md) можно использовать для приведения примитивных типов, но для преобразование, [safe_cast](../windows/safe-cast-cpp-component-extensions.md) или приведение в стиле (который реализуется как [safe_cast](../windows/safe-cast-cpp-component-extensions.md)) необходимо использовать.

- Проверяемая функция не может содержать [оператор reinterpret_cast](../cpp/reinterpret-cast-operator.md) (или любыми другими приведение в стиле C).

- Проверяемая функция нельзя выполнить над [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md). Он только назначьте ему и ее разыменовании.

- Проверяемая функция может выдать или перехватить только указатели для ссылочных типов, типов значений должны упаковываться перед вызовом.

- Проверяемая функция может вызывать только проверяемые функции (таким образом, что вызовы общеязыковая среда выполнения не разрешены, включают `AtEntry` / `AtExit`, и поэтому не разрешены глобальные конструкторы).

- Проверяемый класс нельзя использовать <xref:System.Runtime.InteropServices.LayoutKind>.

- При построении EXE-файла, функция main нельзя объявлять любые параметры, поэтому <xref:System.Environment.GetCommandLineArgs%2A> должен использоваться для получения аргументов командной строки.

- Невиртуальный вызов виртуальной функции. Пример:

   ```cpp
   // not_verifiable.cpp
   // compile with: /clr
   ref struct A {
      virtual void Test() {}
   };

   ref struct B : A {};

   int main() {
      B^ b1 = gcnew B;
      b1->A::Test();   // Non-virtual call to virtual function
   }
   ```

Кроме того следующие ключевые слова не может использоваться в проверяемом коде:

- [неуправляемые](../preprocessor/managed-unmanaged.md) и [пакет](../preprocessor/pack.md) директивы pragma

- [naked](../cpp/naked-cpp.md) и [выравнивание](../cpp/align-cpp.md) [__declspec](../cpp/declspec.md) модификаторы

- [__asm](../assembler/inline/asm.md)

- [__based](../cpp/based-grammar.md)

- [__try](../cpp/try-except-statement.md) и `__except`

## <a name="see-also"></a>См. также

- [Чистый и проверяемый код (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
