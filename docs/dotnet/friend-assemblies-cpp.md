---
title: "Дружественные сборки (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "дружественные сборки, Visual C++"
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Дружественные сборки (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Применимые для выполнения, функция языка *дружественных сборок* делает типы, в области пространства имен или глобальной области в компоненте сборки расположены в одном или нескольких сборки клиента или .netmodules.  
  
## Все среды выполнения  
 **Примечания**  
  
 \(Эта функция языка не поддерживается во всех выполнении\).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Примечания**  
  
 \(Эта функция языка не поддерживается в [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]\).  
  
### Требования  
 Параметр компилятора: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Примечания**  
  
#### Сделать типы в области пространства имен или глобальной области в компоненте сборки расположены на сборку клиента или .netmodule  
  
1.  В компоненте, задайте атрибут сборки <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и передайте имя сборки клиента или .netmodule, доступа к типам в области пространства имен или глобальной области в компоненте.  Можно указать несколько сборки клиента или .netmodules следует указать дополнительные атрибуты.  
  
2.  В сборке клиента или .netmodule, при ссылке на сборку компонент с помощью `#using` передайте атрибут `as_friend`.  Если указать атрибут `as_friend` для сборки, которая не определяет `InternalsVisibleToAttribute`, создается исключение времени выполнения при попытке получить тип в области пространства имен или глобальной области в компоненте.  
  
 Ошибка построения приведет к, если сборка, которая содержит атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> нет строгого имени и клиентов, сборка, используется атрибут `as_friend` действий.  
  
 Хотя типы в области пространства имен и глобальной области можно узнать в сборке клиента или .netmodule, специальные возможности члена продолжает действовать.  Например, невозможно получить доступ к закрытого члена.  
  
 Доступ ко всем типам сборки необходимо явно предоставить.  Например, сборка C не имеет доступ ко всей сборке a типов, если сборка C ссылается на сборку B и сборка B имеет доступ ко всем сборки а. типов.  
  
 Дополнительные сведения об определении специальных возможностей типов вне сборки см. в разделе [Видимость типов](../Topic/Type%20Visibility.md).  
  
 Сведения о том, как в знаком, как задать строгое имя к — сборке, созданной с помощью компилятора Visual C\+\+ см. в разделе [Сборки со строгими именами \(подписывание сборок\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 В качестве альтернативы использованию функции дружественных сборок, можно использовать <xref:System.Security.Permissions.StrongNameIdentityPermission> ограничить доступ к отдельным типы.  
  
### Требования  
 Параметр компилятора: **\/clr**  
  
### Примеры  
 В следующем примере определяется компонент, который определяет сборку клиента, имеющим доступ к типам компонент.  
  
```  
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
  
 В следующем примере кода получить закрытый тип в компоненте.  
  
```  
// friend_assemblies_2.cpp  
// compile by using: /clr  
#using "friend_assemblies.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **Output**  
  
 `Class1::Test_Public`  
  
 В следующем примере определяется компонент, но не указывает сборку клиента, которая будет иметь доступ к типам компонент.  
  
 Обратите внимание, что компонент связан с помощью **\/opt:noref**.  Это гарантирует, что закрытым типам выдаются в метаданные компонента, не требуется, если атрибут `InternalsVisibleTo` будет присутствовать.  Для получения дополнительной информации см. [Параметр \/OPT \(оптимизация\)](../build/reference/opt-optimizations.md).  
  
```  
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
  
 В следующем примере кода определяется клиент, который пытается получить закрытый тип в компоненте, не предоставляет доступ к его закрытым типам.  Из\-за расширения функциональности выполнения, если требуется перехватывать исключение, необходимо попытаться получить закрытый тип во вспомогательной функции.  
  
```  
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
  
 **Output**  
  
 `caught an exception`  
  
 В следующем примере кода показано, как создать компонент строгого имени, определяющий сборку клиента, которая будет иметь доступ к типам компонент.  
  
```  
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
  
 Обратите внимание, что компонент должен определять его открытого ключа.  Рекомендуется ознакомиться, которые последовательно выполните следующие команды в командной строке создать пару ключей и получить открытый ключ:  
  
 **sn \-d friend\_assemblies.snk**  
  
 **sn \-k friend\_assemblies.snk**  
  
 **sn \-i friend\_assemblies.snk friend\_assemblies.snk**  
  
 **sn \-pc friend\_assemblies.snk key.publickey**  
  
 **sn \-tp key.publickey**  
  
 В следующем примере кода получить закрытый тип в компоненте строгого имени.  
  
```  
// friend_assemblies_6.cpp  
// compile by using: /clr /link /keyfile:friend_assemblies.snk  
#using "friend_assemblies_5.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
 **Output**  
  
 `Class1::Test_Public`  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)