---
title: Дружественные сборки (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: e469556a773ffcdbf50e53d94022c0b6b7abf869
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404433"
---
# <a name="friend-assemblies-c"></a>Дружественные сборки (C++)

Для применимых сред выполнения *дружественных сборок* языковое средство делает типы, которые находятся в области видимости пространства имен или глобальной области в компоненте сборки доступными для одного или нескольких клиентских сборок, или netmodules-файлы.

## <a name="all-runtimes"></a>Все среды выполнения

**Заметки**

(Эта возможность языка не поддерживается во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

**Заметки**

(В среде выполнения Windows эта возможность языка не поддерживается.)

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

## <a name="common-language-runtime"></a>Среда CLR

**Заметки**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Чтобы сделать доступным для клиентской сборки или NETMODULE-файл типов в области видимости пространства имен или глобальной области в компоненте сборки

1. В компоненте, укажите атрибут сборки <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>и передайте имя клиентской сборки или .netmodule, который получит доступ к типов в области видимости пространства имен или глобальной области в компоненте.  Можно указать несколько клиентских сборок или netmodules-файлы, указав дополнительные атрибуты.

1. В клиентской сборки или .netmodule, при ссылке на сборку компонента с помощью `#using`, передайте `as_friend` атрибута.  Если указать `as_friend` атрибут для сборки, не соответствует `InternalsVisibleToAttribute`, будет создано исключение времени выполнения при попытке доступа к типу в области видимости пространства имен или глобальной области в компоненте.

Приведет к ошибке построения, если сборка, которая содержит <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> атрибут не имеет строгого имени, но сборку клиента, которая использует `as_friend` атрибут не.

Несмотря на то, что для клиентской сборки или NETMODULE-файл может быть известен типами в области видимости пространства имен и в глобальной области видимости, доступность членов является остается в силе.  К примеру нельзя получить доступ к закрытому члену.

Ко всем типам в сборке, должен быть явно предоставлен доступ.  Например сборка C имеет доступ ко всем типам в сборке А если сборка C ссылается на сборку B, а сборка B имеет доступ ко всем типам в сборке A.

Сведения о том, как подписать — то есть как можно присвоить строгое имя — сборки, созданное с помощью визуального C++ компилятора, см. в разделе [сборки со строгими именами (подписывание сборок) (C++выполняет)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

В качестве альтернативы использованию дружественные сборки, можно использовать <xref:System.Security.Permissions.StrongNameIdentityPermission> для ограничения доступа к отдельным типам.

### <a name="requirements"></a>Требования

Параметр компилятора: **/clr**

### <a name="examples"></a>Примеры

В следующем примере кода определяется компонентом, который указывает сборку клиента, которая имеет доступ к типам в компоненте.

```cpp
// friend_assemblies.cpp
// compile by using: /clr /LD
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type
[assembly:InternalsVisibleTo("friend_assemblies_2")];

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

В следующем примере кода обращается к закрытый тип компонента.

```cpp
// friend_assemblies_2.cpp
// compile by using: /clr
#using "friend_assemblies.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

В следующем примере кода определяется компонент, но не содержит сборку клиента, которая будет иметь доступ к типам в компоненте.

Обратите внимание на то, что компонент уже связан с помощью **/ opt: noref**. Это гарантирует, что закрытые типы преобразуются в метаданных компонента, который является не обязательным, если `InternalsVisibleTo` присутствует атрибут. Дополнительные сведения см. в разделе [/OPT (оптимизации)](../build/reference/opt-optimizations.md).

```cpp
// friend_assemblies_3.cpp
// compile by using: /clr /LD /link /opt:noref
using namespace System;

ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

В следующем примере кода определяется клиент, который пытается получить доступ к закрытый тип в компоненте, который не предоставляет доступ к закрытым типам, его. Из-за поведения среды выполнения Если требуется перехватывать исключения, необходимо попытки обращения к закрытый тип в вспомогательную функцию.

```cpp
// friend_assemblies_4.cpp
// compile by using: /clr
#using "friend_assemblies_3.dll" as_friend
using namespace System;

void Test() {
   Class1 ^ a = gcnew Class1;
}

int main() {
   // to catch this kind of exception, use a helper function
   try {
      Test();
   }
   catch(MethodAccessException ^ e) {
      Console::WriteLine("caught an exception");
   }
}
```

```Output
caught an exception
```

В следующем примере кода показано, как создать компонент строгого имени, который указывает сборку клиента, которая будет иметь доступ к типам в компоненте.

```cpp
// friend_assemblies_5.cpp
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk
using namespace System::Runtime::CompilerServices;
using namespace System;
// an assembly attribute, not bound to a type

[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];

private ref class Class1 {
public:
   void Test_Public() {
      Console::WriteLine("Class1::Test_Public");
   }
};
```

Обратите внимание на то, что компонент необходимо указать свой открытый ключ. Мы рекомендуем, выполните последовательно следующие команды в командной строке, чтобы создать пару ключей и получить открытый ключ:

**sn -d friend_assemblies.snk**

**sn -k friend_assemblies.snk**

**sn -i friend_assemblies.snk friend_assemblies.snk**

**sn -pc friend_assemblies.snk key.publickey**

**Sn - tp key.publickey**

В следующем примере кода обращается к закрытый тип в компоненте строгого имени.

```cpp
// friend_assemblies_6.cpp
// compile by using: /clr /link /keyfile:friend_assemblies.snk
#using "friend_assemblies_5.dll" as_friend

int main() {
   Class1 ^ a = gcnew Class1;
   a->Test_Public();
}
```

```Output
Class1::Test_Public
```

## <a name="see-also"></a>См. также

[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)
