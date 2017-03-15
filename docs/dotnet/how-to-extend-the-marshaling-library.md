---
title: "Практическое руководство. Расширение библиотеки маршалинга | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "маршалинг библиотеки, расширение"
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Практическое руководство. Расширение библиотеки маршалинга
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе рассматриваются способы расширения библиотеки маршалинга для обеспечения больших возможностей преобразования типов данных.  Пользователи могут расширить библиотеку маршалинга для выполнения любых преобразований, которые не поддерживаются библиотекой в настоящий момент.  
  
 Расширить библиотеку маршалинга можно одним из двух способов: с помощью [Класс marshal\_context](../dotnet/marshal-context-class.md) или без него.  Ознакомьтесь с разделом [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md), чтобы определить, необходим ли для нового преобразования контекст.  
  
 В обоих случаях сначала для нового преобразований маршалинга создается файл.  Это необходимо для сохранения целостности стандартных файлов библиотеки маршалинга.  Если необходимо переместить проект на другой компьютер или передать его другому программисту, то вместе с проектом необходимо скопировать файл для маршалинга.  Таким образом, гарантируется, что пользователь, получающий проект, обретает возможность выполнять новые преобразования без необходимости изменять какие\-либо файлы библиотеки.  
  
### Включение в библиотеку маршалинга функции для нового преобразования, для которого не требуется контекст  
  
1.  Создайте файл для хранения новых функций маршалинга, например MyMarshal.h.  
  
2.  Включите один или несколько файлов из библиотеки маршалинга:  
  
    -   Marshal.h для базовых типов;  
  
    -   Marshal\_windows.h для типов данных Windows;  
  
    -   Marshal\_cppstd.h для типов данных STL;  
  
    -   Marshal\_atl.h для типов данных ATL.  
  
3.  После выполнения этих действий используйте приведенный код для написания функции преобразования.  В этом коде "TO" означает тип, в который выполняется преобразование, "FROM" — преобразуемый тип, а `from` — преобразуемый параметр.  
  
4.  Необходимо заменить примечание о логике преобразования на код, чтобы выполнить преобразование параметра `from` в объект типа "TO" и вывести преобразованный объект.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### Включение в библиотеку маршалинга функции для нового преобразования, для которого требуется контекст  
  
1.  Создайте файл для хранения новых функций маршалинга, например MyMarshal.h  
  
2.  Включите один или несколько файлов из библиотеки маршалинга:  
  
    -   Marshal.h для базовых типов;  
  
    -   Marshal\_windows.h для типов данных Windows;  
  
    -   Marshal\_cppstd.h для типов данных STL;  
  
    -   Marshal\_atl.h для типов данных ATL.  
  
3.  После выполнения этих действий используйте приведенный код для написания функции преобразования.  В этом коде "TO" означает тип, в который выполняется преобразование, "FROM" — преобразуемый тип, `toObject` — указатель для хранения результата, а `fromObject` — преобразуемый параметр.  
  
4.  Следует заменить примечание об инициализации на код для инициализации `toPtr` с соответствующим пустым значением.  Например, для указателя необходимо задать значение `NULL`.  
  
5.  Необходимо заменить примечание о логике преобразования на код, чтобы выполнить преобразование параметра `from` в объект типа *TO*.  Преобразованный объект будет храниться в `toPtr`.  
  
6.  Необходимо заменить примечание о задании значения для указателя `toObject` на код, чтобы задать в качестве значения для `toObject` преобразованный объект.  
  
7.  Необходимо заменить примечание об очистке собственных ресурсов на код, чтобы освободить память, выделенную `toPtr`.  Если `toPtr` выделяет память с помощью `new`, для ее освобождения следует использовать `delete`.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## Пример  
 В следующем примере в библиотеку маршалинга включается новое преобразование, для которого не требуется контекст.  В этом примере код преобразует информацию о сотрудниках из собственного типа данных в управляемый.  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 В предыдущем примере функция `marshal_as` возвращает дескриптор преобразованных данных.  Это необходимо для предотвращения создания дополнительной копии данных.  Возвращение переменной напрямую приведет к неоправданному снижению производительности.  
  
  **Управляемое имя: Jeff Smith**  
**Управляемый адрес: 123 Main Street**  
**Управляемый индекс: 98111**   
## Пример  
 В следующем примере выполняется преобразование информации о сотрудниках из управляемого типа данных в собственный.  Для выполнения данного преобразования требуется контекст маршалинга.  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
  **Исходное имя: Jeff Smith**  
**Исходный адрес: 123 Main Street**  
**Исходный индекс: 98111**   
## См. также  
 [Общие сведения о маршалировании в C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)