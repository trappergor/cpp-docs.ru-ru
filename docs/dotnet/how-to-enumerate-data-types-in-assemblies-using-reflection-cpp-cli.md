---
title: "Практическое руководство. Перечисление типов данных в сборках с помощью отражения (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "сборки [C++]"
  - "сборки [C++], перечисление типов данных в"
  - "типы данных [C++], перечисление"
  - "открытые члены [C++]"
  - "открытые типы [C++]"
  - "отражение [C++], внешние сборки"
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Перечисление типов данных в сборках с помощью отражения (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода демонстрируется перечисление открытых типов и членов с помощью <xref:System.Reflection>.  
  
 При задании имени сборки, находящейся в локальном каталоге либо в глобальном кэше сборок, следующий код предпринимает попытку открыть ее и извлечь ее описание.  В случае успеха отображаются все типы с соответствующими открытыми членами.  
  
 Обратите внимание, что при использовании метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> имена файлов должны указываться без расширения.  Поэтому при использовании имени "mscorlib.dll" в качестве аргумента командной строки произойдет сбой, а при использовании имени "mscorlib" будет выведен список типов .NET Framework.  Если имя сборки не указано, данный код выведет сведения о типах, имеющихся в текущей сборке \(EXE\-файл на основе данного кода\).  
  
## Пример  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## См. также  
 [Отражение](../dotnet/reflection-cpp-cli.md)