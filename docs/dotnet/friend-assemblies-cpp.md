---
title: Дружественные сборки (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: a42caaf07f6ec0c71f63d6a0df8a79fff6f737e6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221449"
---
# <a name="friend-assemblies-c"></a>Дружественные сборки (C++)

Для применимых сред выполнения функция языка *дружественных сборок* делает типы, находящиеся в области видимости пространства имен или глобальной области в компоненте сборки, доступными для одной или нескольких клиентских сборок или NETMODULE.

## <a name="all-runtimes"></a>Все среды выполнения

**Замечания**

(Эта функция языка не поддерживается во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

**Замечания**

(В среде выполнения Windows эта возможность языка не поддерживается.)

### <a name="requirements"></a>Требования

Параметр компилятора: **/ZW**

## <a name="common-language-runtime"></a>Среда CLR

**Замечания**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Создание типов в области видимости пространства имен или глобальной области в компоненте сборки, доступном для клиентской сборки или. netmodule

1. В компоненте укажите атрибут сборки <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и передайте имя клиентской сборки или NETMODULE, который будет обращаться к типам в области пространства имен или глобальной области в компоненте.  Можно указать несколько клиентских сборок или NETMODULE, указав дополнительные атрибуты.

1. В клиентской сборке или NETMODULE при ссылке на сборку компонента с помощью `#using` следует передать **`as_friend`** атрибут.  Если указать **`as_friend`** атрибут для сборки, которая не указана, при `InternalsVisibleToAttribute` попытке доступа к типу в области пространства имен или глобальной области в компоненте будет выдано исключение времени выполнения.

Ошибка сборки возникает, если сборка, содержащая <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> атрибут, не имеет строгого имени, а Клиентская сборка, использующая атрибут, имеет значение **`as_friend`** .

Хотя типы в области видимости пространства имен и глобальной области могут быть известны клиентской сборке или NETMODULE, доступность членов по-прежнему действует.  Например, нельзя получить доступ к закрытому члену.

Доступ ко всем типам в сборке должен быть явно предоставлен.  Например, сборка C не имеет доступа ко всем типам в сборке а, если сборка C ссылается на сборку B, а сборка б имеет доступ ко всем типам в сборке A.

Сведения о том, как присвоить строгое имя сборки (сборке, построенной с помощью компилятора Microsoft C++), см. в разделе [сборки со строгими именами (подписывание сборок) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

В качестве альтернативы использованию функции дружественных сборок можно использовать <xref:System.Security.Permissions.StrongNameIdentityPermission> для ограничения доступа к отдельным типам.

### <a name="requirements"></a>Требования

Параметр компилятора: **/clr**

### <a name="examples"></a>Примеры

В следующем примере кода определяется компонент, указывающий клиентскую сборку, имеющую доступ к типам в компоненте.

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

Следующий пример кода обращается к закрытому типу в компоненте.

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

В следующем примере кода определяется компонент, но не указывается Клиентская сборка, которая будет иметь доступ к типам в компоненте.

Обратите внимание, что компонент связан с помощью **/OPT: NOREF**. Это гарантирует, что закрытые типы будут выдаваться в метаданных компонента, что не требуется при `InternalsVisibleTo` наличии атрибута. Дополнительные сведения см. в статье [Параметр /OPT (оптимизация)](../build/reference/opt-optimizations.md).

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

В следующем примере кода определяется клиент, пытающийся получить доступ к закрытому типу в компоненте, который не предоставляет доступ к его закрытым типам. Из-за поведения среды выполнения, если необходимо перехватить исключение, необходимо попытаться получить доступ к закрытому типу в вспомогательной функции.

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

В следующем примере кода показано, как создать компонент со строгим именем, указывающий клиентскую сборку, которая будет иметь доступ к типам в компоненте.

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

Обратите внимание, что компонент должен указать его открытый ключ. Мы рекомендуем последовательно выполнять следующие команды в командной строке, чтобы создать пару ключей и получить открытый ключ:

**SN-d friend_assemblies. snk**

**sn-k friend_assemblies. snk**

**sn-i friend_assemblies. snk friend_assemblies. snk**

**SN-PC friend_assemblies. snk Key. publickey**

**sn -tp key.publickey**

Следующий пример кода обращается к закрытому типу в компоненте строгого имени.

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

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md)
