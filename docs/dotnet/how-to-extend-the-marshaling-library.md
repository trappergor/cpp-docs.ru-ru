---
title: "Как: расширение библиотеки маршалинга | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords: Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ee919e1faa37959d25e8e42581c8cde80d640337
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-extend-the-marshaling-library"></a>Практическое руководство. Расширение библиотеки маршалинга
В этом разделе описывается расширение библиотеки маршалинга для предоставления дополнительных преобразований между типами данных. Пользователи могут расширить библиотеку маршалинга для выполнения любых преобразований, не поддерживаемых в библиотеку.  
  
 Можно расширить библиотеку маршалинга в одном из двух способов: с или без [класс marshal_context](../dotnet/marshal-context-class.md). Просмотрите [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) раздел, чтобы определить, требуется ли нового преобразования контекст.  
  
 В обоих случаях сначала создайте файл для нового преобразований маршалинга. Это необходимо для сохранения целостности стандартных файлов библиотеки маршалинга. Если вы хотите переместить проект на другой компьютер или другим программистам, необходимо скопировать файл вместе с остальными участниками проекта для маршалинга. Таким образом пользователь, получающий проект будут гарантированно получать новые преобразования и не придется изменять файлы всех необходимых библиотек.  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Для расширения библиотеки маршалинга с преобразованием, которое требуется контекст  
  
1.  Создайте файл для хранения новых функций маршалинга, например MyMarshal.h.  
  
2.  Включать один или несколько файлов библиотеки маршалинга:  
  
    -   Marshal.h для базовых типов.  
  
    -   marshal_windows.h для типов данных windows.  
  
    -   marshal_cppstd.h для типов данных стандартной библиотеки C++.  
  
    -   marshal_atl.h для ATL типов данных.  
  
3.  Код в конце эти шаги можно используйте для написания функции преобразования. В этом коде, чтобы тип преобразования, FROM является целевой тип преобразования, и `from` является преобразуемый параметр.  
  
4.  Замените код для преобразования Примечание о логике преобразования `from` параметр в объект TO типа и возвращает преобразованный объект.  
  
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
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Для расширения библиотеки маршалинга с преобразованием, которое требуется контекст  
  
1.  Создайте файл для хранения новых функций маршалинга, например MyMarshal.h  
  
2.  Включать один или несколько файлов библиотеки маршалинга:  
  
    -   Marshal.h для базовых типов.  
  
    -   marshal_windows.h для типов данных windows.  
  
    -   marshal_cppstd.h для типов данных стандартной библиотеки C++.  
  
    -   marshal_atl.h для ATL типов данных.  
  
3.  Код в конце эти шаги можно используйте для написания функции преобразования. В этом коде, чтобы тип преобразования, FROM является целевой тип преобразования, `toObject` является указателем, в котором для хранения результата, и `fromObject` является преобразуемый параметр.  
  
4.  Замените Комментарий об инициализации на код для инициализации `toPtr` соответствующим пустым значением. Например, если указатель, присвоить его `NULL`.  
  
5.  Замените код для преобразования Примечание о логике преобразования `from` параметр в объект *TO* типа. Преобразованный объект будет храниться в `toPtr`.  
  
6.  Замените комментарий о параметре `toObject` с кодом, чтобы задать `toObject` преобразованный объект.  
  
7.  Замените Комментарий об очистке собственных ресурсов на код, чтобы освободить память, выделенная `toPtr`. Если `toPtr` выделяет память с помощью `new`, используйте `delete` для освобождения памяти.  
  
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
  
## <a name="example"></a>Пример  
 В следующем примере расширяется библиотеке маршалинга с преобразованием, которое требуется контекст. В этом примере код преобразует сведения о сотрудниках из собственного типа данных в управляемый тип данных.  
  
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
  
 В предыдущем примере `marshal_as` функция возвращает дескриптор преобразованных данных. Это было сделано, чтобы избежать создания дополнительной копии данных. Возвращение переменной напрямую бы затрат производительности связаны с ним.  
  
```Output  
Managed name: Jeff Smith  
Managed address: 123 Main Street  
Managed zip code: 98111  
```  
  
## <a name="example"></a>Пример  
 В следующем примере преобразуется сведения о сотрудниках из управляемого типа данных в тип данных в собственном формате. Этого преобразования требуется контекст маршалинга.  
  
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
  
```Output  
Native name: Jeff Smith  
Native address: 123 Main Street  
Native zip code: 98111  
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)