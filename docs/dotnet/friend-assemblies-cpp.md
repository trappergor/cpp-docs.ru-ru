---
title: Дружественные сборки (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cc39fa66a73f16f800f0c7f0e4bbc49730d4b9c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33113763"
---
# <a name="friend-assemblies-c"></a>Дружественные сборки (C++)
Для применимых сред выполнения *дружественных сборок* функции языка делает типы, которые находятся в области видимости пространства имен или глобальной области в компоненте сборки доступны для одного или нескольких клиентских сборок или NETMODULE.  
  
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
  
#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Чтобы предоставить доступ к клиентской сборки или NETMODULE-файл типов в глобальной области видимости или области видимости пространства имен в компоненте сборки  
  
1.  В компоненте, укажите атрибут сборки <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>и передайте имя клиентской сборки или NETMODULE-файл, который будет иметь доступ к типам в области видимости пространства имен или глобальной области в компоненте.  Можно указать несколько клиентских сборок или NETMODULE-файлов, указав дополнительные атрибуты.  
  
2.  В клиентской сборки или NETMODULE-файл, при ссылке на сборку компонента с помощью `#using`, передайте `as_friend` атрибута.  При указании `as_friend` атрибут для сборки, не соответствует `InternalsVisibleToAttribute`, будет создано исключение времени выполнения, при попытке доступа к типу, в области видимости пространства имен или глобальной области в компоненте.  
  
 Приведет к ошибке сборки, если сборка, содержащая <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> атрибут не имеет строгого имени, но сборку клиента, которая использует `as_friend` атрибут не.  
  
 Несмотря на то, что для клиентской сборки или NETMODULE-файл может быть известен типов в глобальной области видимости и в области видимости пространства имен, доступность члена действует по-прежнему.  Например нельзя получить доступ к закрытого члена.  
  
 Необходимо явным образом предоставлен доступ ко всем типам в сборке.  Например сборка C имеет доступ ко всем типам в сборке А если сборка C ссылается на сборку B, а сборка B имеет доступ ко всем типам в сборке A.  
  
 Сведения о том, как присвоить — то есть, как для создания строгого имени для — сборку, которая создается с помощью компилятора Visual C++, см. [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 В качестве альтернативы дружественные сборки можно использовать <xref:System.Security.Permissions.StrongNameIdentityPermission> для ограничения доступа к отдельным типам.  
  
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
  
 В следующем примере кода определяется компонент, но не указывает сборку клиента, которая будет иметь доступ к типам в компоненте.  
  
 Обратите внимание, что компонент уже связан с помощью **/ opt: noref**. Это гарантирует, что закрытые типы передаются в метаданные компонента, который не является обязательным при `InternalsVisibleTo` присутствует атрибут. Дополнительные сведения см. в разделе [/OPT (оптимизации)](../build/reference/opt-optimizations.md).  
  
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
  
 В следующем примере кода определяется клиент, который пытается получить доступ к закрытый тип в компоненте, который не предоставляет доступа к закрытым типам, его. Из-за поведение среды выполнения Если требуется перехватывать исключения, следует пытаться закрытый тип в вспомогательную функцию доступа.  
  
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
  
 Обратите внимание, что компонент должен указать свой открытый ключ. Рекомендуется использовать выполняются последовательно следующие команды в командной строке, чтобы создать пару ключей и получить открытый ключ.  
  
 **Sn -d friend_assemblies.snk**  
  
 **sn -k friend_assemblies.snk**  
  
 **sn -i friend_assemblies.snk friend_assemblies.snk**  
  
 **key.publickey friend_assemblies.snk Sn -ПК**  
  
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
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)