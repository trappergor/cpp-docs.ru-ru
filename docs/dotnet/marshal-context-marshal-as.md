---
title: marshal_context::marshal_as | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f88d086c76ea6b56f1bb049b886df70ceadbdbb9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707906"
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as
Выполняет маршалинг на конкретный объект данных для преобразования между управляемого и собственного типа данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### <a name="parameters"></a>Параметры  
*Входные данные*<br/>
[in] Значение, которое требуется маршалировать `To_Type` переменной.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Переменная типа `To_Type` , представляющий преобразованное значение из `input`.  
  
## <a name="remarks"></a>Примечания  
 Эта функция выполняет маршалинг на конкретный объект данных. Эту функцию можно использовать только с преобразованиями, обозначается в таблице в [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 При попытке маршалинга типов данных, которые не поддерживаются, пару `marshal_as` приведет к ошибке [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Читает сообщение, в состав сведения об этой ошибке. `C4996` Ошибка может возникать для более чем просто нерекомендуемые функции. Два условия, которые создает эту ошибку попытке маршалировать пару типов данных, которые не поддерживаются и попытаться использовать `marshal_as` для преобразования, который требуется контекст.  
  
 Библиотека маршалинга состоит из нескольких файлов заголовка. Любые преобразования требуется только один файл, но может включать дополнительные файлы, если необходимо выполнить другие преобразования. В таблице в `Marshaling Overview in C++` указывает, какой маршалинга файл должен быть включен для каждого преобразования.  
  
## <a name="example"></a>Пример  
 В этом примере создает контекст для маршалинга из `System::String` для `const char *` тип переменной. Преобразованные данные, не будет допустимым после строки, которая удаляет контекст.  
  
```  
// marshal_context_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   marshal_context^ context = gcnew marshal_context();  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = context->marshal_as<const char*>( message );  
   delete context;  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >  
  
 **Пространство имен:** msclr::interop  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [Класс marshal_context](../dotnet/marshal-context-class.md)