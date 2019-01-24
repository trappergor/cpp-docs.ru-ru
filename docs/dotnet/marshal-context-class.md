---
title: Класс marshal_context
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 25fc2be80ba0e5d8c7f76cee1f22eed4d1bb4fc7
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805985"
---
# <a name="marshalcontext-class"></a>Класс marshal_context

Этот класс преобразует данные между собственной и управляемой средами.

## <a name="syntax"></a>Синтаксис

```cpp
class marshal_context
```

## <a name="remarks"></a>Примечания

Используйте `marshal_context` класс для преобразования данных, требуется контекст. Дополнительные сведения о какие преобразования требуется контекст и маршалинга файл, который должен быть вставлен, см. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md). Результат операций маршалинга при использовании контекста действителен только до `marshal_context` уничтожении объекта. Для сохранения результатов, необходимо скопировать данные.

Же `marshal_context` может использоваться для множество преобразований данных. Повторное использование контекста таким образом не влияет на результаты предыдущих маршалинга вызовов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание| 
|---------|-----------| 
|[marshal_context::marshal_context](#marshal-context)|Создает `marshal_context` объект, используемый для преобразования данных между типами данных, управляемый и машинный.| 
|[marshal_context::~marshal_context](#tilde-marshal-context)|Уничтожает объект `marshal_context`.| 

### <a name="public-methods"></a>Открытые методы

|name|Описание| 
|---------|-----------| 
|[marshal_context::marshal_as](#marshal-as)|Выполняет маршалинг на конкретный объект данных для преобразования между управляемого и собственного типа данных.| 


## <a name="requirements"></a>Требования

**Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >

**Пространство имен:** msclr::interop

## <a name="marshal-context"></a>marshal_context::marshal_context

Создает `marshal_context` объект, используемый для преобразования данных между типами данных, управляемый и машинный.

```cpp
marshal_context();
```

### <a name="remarks"></a>Примечания

Некоторые преобразования данных требуется контекст маршалинга. Дополнительные сведения о том, какие переводы требуется контекст и какие маршалинг файла, с которым необходимо включить в приложение, см. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Пример

См. в примере [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).


## <a name="tilde-marshal-context"></a>marshal_context::~marshal_context

Уничтожает объект `marshal_context`.

```cpp
~marshal_context();
```

### <a name="remarks"></a>Примечания

Некоторые преобразования данных требуется контекст маршалинга. См. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какой переводы требуется контекст и какие маршалинга файл должен быть включены в приложении.

Удаление `marshal_context` объект сделает данные, преобразованные в этом контексте. Если вы хотите сохранить данные после `marshal_context` уничтожении объекта, необходимо вручную скопировать данные на переменную, которая будет сохраняться.

## <a name="marshal-as"></a>marshal_context::marshal_as

Выполняет маршалинг на конкретный объект данных для преобразования между управляемого и собственного типа данных.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Параметры

*Входные данные*<br/>
[in] Значение, которое требуется маршалировать `To_Type` переменной.

### <a name="return-value"></a>Возвращаемое значение

Переменная типа `To_Type` это преобразованное значение `input`.

### <a name="remarks"></a>Примечания

Эта функция выполняет маршалинг на конкретный объект данных. Эту функцию можно использовать только с преобразованиями, обозначается в таблице в [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md).

При попытке маршалинга пару типов данных, которые не поддерживаются, `marshal_as` приведет к ошибке [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Читает сообщение, в состав сведения об этой ошибке. `C4996` Ошибка может возникать для более чем просто нерекомендуемые функции. Два условия, которые создает эту ошибку попытке маршалировать пару типов данных, которые не поддерживаются и попытаться использовать `marshal_as` для преобразования, который требуется контекст.

Библиотека маршалинга состоит из нескольких файлов заголовка. Любые преобразования требуется только один файл, но может включать дополнительные файлы, если необходимо выполнить другие преобразования. В таблице в `Marshaling Overview in C++` указывает, какой маршалинга файл должен быть включен для каждого преобразования.

### <a name="example"></a>Пример

В этом примере создает контекст для маршалинга из `System::String` для `const char *` тип переменной. После строки, которая удаляет контекст преобразованных данных будут недопустимы.

```cpp
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