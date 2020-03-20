---
title: Практическое руководство. Расширение библиотеки маршалинга
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
ms.openlocfilehash: ab3b17638e07a54189803c83163db67c5ebf82a5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545273"
---
# <a name="how-to-extend-the-marshaling-library"></a>Практическое руководство. Расширение библиотеки маршалинга

В этом разделе объясняется, как расширить библиотеку для упаковки, чтобы обеспечить больше преобразований между типами данных. Пользователи могут расширить библиотеку упаковки для любых преобразований данных, которые в настоящее время не поддерживаются библиотекой.

Расширение библиотеки можно расширить одним из двух способов: с [классом marshal_context](../dotnet/marshal-context-class.md)или без него. Ознакомьтесь с [обзором упаковки в C++ ](../dotnet/overview-of-marshaling-in-cpp.md) разделе, чтобы определить, требуется ли для нового преобразования контекст.

В обоих случаях сначала создается файл для новых преобразований маршалирования. Это позволяет сохранить целостность стандартных файлов библиотеки стандартизованного хранения. Если требуется перенести проект на другой компьютер или на другого программиста, необходимо скопировать новый файл упаковки вместе с остальной частью проекта. Таким образом, пользователь, получивший проект, будет гарантированно получать новые преобразования и не должен будет изменять файлы библиотеки.

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Расширение библиотеки маршалирования с помощью преобразования, не требующего контекста

1. Создайте файл для хранения новых функций маршалирования, например Мимаршал. h.

1. Включите один или несколько файлов библиотеки маршалирования:

   - Marshal. h для базовых типов.

   - marshal_windows. h для типов данных Windows.

   - marshal_cppstd. h для C++ типов данных стандартных библиотек.

   - marshal_atl. h для типов данных ATL.

1. Используйте код в конце этих шагов, чтобы написать функцию преобразования. В этом коде — тип для преобразования, FROM — тип для преобразования, а `from` — преобразуемый параметр.

1. Замените комментарий логики преобразования на код, чтобы преобразовать параметр `from` в объект типа и вернуть преобразованный объект.

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

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Расширение библиотеки маршалирования с помощью преобразования, для которого требуется контекст

1. Создайте файл для хранения новых функций маршалирования, например Мимаршал. h.

1. Включите один или несколько файлов библиотеки маршалирования:

   - Marshal. h для базовых типов.

   - marshal_windows. h для типов данных Windows.

   - marshal_cppstd. h для C++ типов данных стандартных библиотек.

   - marshal_atl. h для типов данных ATL.

1. Используйте код в конце этих шагов, чтобы написать функцию преобразования. В этом коде — тип для преобразования, FROM — это тип для преобразования, `toObject` — это указатель, в котором сохраняется результат, а `fromObject` — преобразуемый параметр.

1. Замените комментарий об инициализации кодом, чтобы инициализировать `toPtr` соответствующим пустым значением. Например, если это указатель, задайте для него значение `NULL`.

1. Замените комментарий логики преобразования на код для преобразования параметра `from` в объект *в* тип. Этот преобразованный объект будет храниться в `toPtr`.

1. Замените комментарий к параметру `toObject` с кодом, чтобы задать `toObject` преобразованному объекту.

1. Замените комментарий об очистке машинных ресурсов с помощью кода, чтобы освободить память, выделенную `toPtr`. Если `toPtr` выделенной памяти с помощью `new`, используйте `delete`, чтобы освободить память.

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

Следующий пример расширяет библиотеку маршалирования с помощью преобразования, для которого не требуется контекст. В этом примере код преобразует сведения о сотруднике из собственного типа данных в управляемый тип данных.

```cpp
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

В предыдущем примере функция `marshal_as` возвращает маркер преобразованных данных. Это было сделано, чтобы предотвратить создание дополнительной копии данных. Возврат переменной напрямую приведет к ненужным затратам на производительность.

```Output
Managed name: Jeff Smith
Managed address: 123 Main Street
Managed zip code: 98111
```

## <a name="example"></a>Пример

В следующем примере сведения о сотруднике преобразуются из управляемого типа данных в собственный тип данных. Для этого преобразования требуется контекст маршалирования.

```cpp
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

## <a name="see-also"></a>См. также:

[Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)
