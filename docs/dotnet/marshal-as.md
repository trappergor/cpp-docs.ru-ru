---
title: marshal_as | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
dev_langs:
- C++
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a209b1ee657d6ae6773ee88c64225a7dc5b4f49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="marshalas"></a>marshal_as
Этот метод преобразует данные между машинным и управляемым средами.  
  
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
 Этот метод является упрощенный способ преобразования данных между неуправляемыми и управляемыми типами. Чтобы определить, какие типы данных поддерживаются, см. [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md). Некоторые преобразования данных требуется контекст. Эти типы данных можно преобразовать с помощью [класс marshal_context](../dotnet/marshal-context-class.md).  
  
 При попытке маршалинга пару типы данных, которые не поддерживаются, `marshal_as` выдаст ошибку [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Прочитайте сообщение, поставляемых вместе с сведения об этой ошибке. `C4996` Ошибка может возникать для более просто нерекомендуемых функций. Одним из примеров пытается маршалировать пару типов данных, которые не поддерживаются.  
  
 Библиотека маршалинга состоит из нескольких файлов заголовков. Какие-либо преобразования требуется только один файл, но может включать дополнительные файлы, при необходимости для других преобразований. Какие преобразования связаны с какие файлы можно найти в таблице в `Marshaling Overview`. В любом случае какие преобразования необходимо сделать, пространство имен требование настроена на срабатывание всегда.  
  
## <a name="example"></a>Пример  
 В этом примере маршалирует из `const char*` для `System::String` тип переменной.  
  
```  
// marshal_as_test.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   const char* message = "Test String to Marshal";  
   String^ result;  
   result = marshal_as<String^>( message );  
   return 0;  
}  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >  
  
 **Пространство имен:** msclr::interop  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [Класс marshal_context](../dotnet/marshal-context-class.md)