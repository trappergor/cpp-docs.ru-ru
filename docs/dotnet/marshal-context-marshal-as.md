---
title: marshal_context::marshal_as | Документы Microsoft
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
ms.openlocfilehash: 27f27b164d7a00e05e8d080a692f97b696776cbe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136211"
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as
Выполняет маршалинг на конкретный объект данных для преобразования между управляемой и собственного типа данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
To_Type marshal_as<To_Type>(  
   From_Type input   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `input`  
 Значение, которое требуется маршалировать `To_Type` переменной.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Переменная типа `To_Type` , преобразованное значение `input`.  
  
## <a name="remarks"></a>Примечания  
 Эта функция выполняет маршалинг на конкретный объект данных. Эту функцию можно использовать только с преобразованиями, обозначенном таблицы в [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md).  
  
 При попытке маршалинга пару типы данных, которые не поддерживаются, `marshal_as` выдаст ошибку [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Прочитайте сообщение, поставляемых вместе с сведения об этой ошибке. `C4996` Ошибка может возникать для более просто нерекомендуемых функций. Два условия, которые создает эту ошибку при попытке маршалинга пару типов данных, которые не поддерживаются и попытаться использовать `marshal_as` для преобразования, который требуется контекст.  
  
 Библиотека маршалинга состоит из нескольких файлов заголовков. Какие-либо преобразования требуется только один файл, но может включать дополнительные файлы, при необходимости для других преобразований. В таблице в `Marshaling Overview in C++` указывает, какие маршалинга файл должен быть включен для каждого преобразования.  
  
## <a name="example"></a>Пример  
 В этом примере создается контекст для маршалинга из `System::String` для `const char *` тип переменной. Преобразованные данные не допустимы после строки, которая удаляет контекст.  
  
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
 [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [Класс marshal_context](../dotnet/marshal-context-class.md)