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
ms.openlocfilehash: aa5935332cfa12c02e8084136a311a7593a4f3b9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508590"
---
# <a name="marshal_context-class"></a>Класс marshal_context

Этот класс преобразует данные между собственными и управляемыми средами.

## <a name="syntax"></a>Синтаксис

```cpp
class marshal_context
```

## <a name="remarks"></a>Remarks

Используйте `marshal_context` класс для преобразований данных, для которых требуется контекст. Дополнительные сведения о том, какие преобразования нуждаются в контексте и какие файлы упакованы должны быть добавлены, см. [в разделе Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md). Результат маршалирования при использовании контекста действителен только до `marshal_context` уничтожения объекта. Чтобы сохранить результат, необходимо скопировать данные.

То же самое `marshal_context` можно использовать для множества преобразований данных. Повторное использование контекста таким способом не повлияет на результаты предыдущих вызовов маршалирования.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Название|Описание|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|Конструирует `marshal_context` объект для использования при преобразовании данных между управляемыми и собственными типами данных.|
|[marshal_context:: ~ marshal_context](#tilde-marshal-context)|Уничтожает объект `marshal_context` .|

### <a name="public-methods"></a>Открытые методы

|Название|Описание|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|Выполняет упаковку для определенного объекта данных, чтобы преобразовать его между управляемым и собственным типами данных.|

## <a name="requirements"></a>Требования

**Заголовочный файл:** \<msclr\marshal.h> , \<msclr\marshal_windows.h> , \<msclr\marshal_cppstd.h> или \<msclr\marshal_atl.h>

**Пространство имен:** мсклр:: Interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a> marshal_context:: marshal_context

Конструирует `marshal_context` объект для использования при преобразовании данных между управляемыми и собственными типами данных.

```cpp
marshal_context();
```

### <a name="remarks"></a>Remarks

Для некоторых преобразований данных требуется контекст маршалирования. Дополнительные сведения о том, какие переводы нуждаются в контексте и какие файлы упакованы необходимо включить в приложение, см. [в разделе Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Пример

См. пример для [marshal_context:: marshal_as](#marshal-as).

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a> marshal_context:: ~ marshal_context

Уничтожает объект `marshal_context` .

```cpp
~marshal_context();
```

### <a name="remarks"></a>Remarks

Для некоторых преобразований данных требуется контекст маршалирования. Дополнительные сведения о том, какие переводы нуждаются в контексте и какие файлы упакованы должны быть добавлены в приложение, см. в разделе Общие сведения о [маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) .

При удалении `marshal_context` объекта данные, преобразованные этим контекстом, станут недействительными. Если вы хотите сохранить данные после `marshal_context` уничтожения объекта, необходимо вручную скопировать данные в переменную, которая будет сохранена.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a> marshal_context:: marshal_as

Выполняет упаковку для определенного объекта данных, чтобы преобразовать его между управляемым и собственным типами данных.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Параметры

*input*<br/>
окне Значение, которое необходимо маршалировать в `To_Type` переменную.

### <a name="return-value"></a>Возвращаемое значение

Переменная типа `To_Type` , преобразованное в значение `input` .

### <a name="remarks"></a>Remarks

Эта функция выполняет упаковку на определенном объекте данных. Используйте эту функцию только с преобразованиями, указанными в таблице в разделе [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md).

При попытке маршалирования пары типов данных, которые не поддерживаются, `marshal_as` выдает ошибку [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) во время компиляции. Дополнительные сведения см. в сообщении, прилагаемом к этой ошибке. Эта `C4996` ошибка может быть создана для более чем нерекомендуемых функций. Два условия, которые создают эту ошибку, пытаются маршалировать пару типов данных, которые не поддерживаются, и пытаться использовать `marshal_as` для преобразования, для которого требуется контекст.

Библиотека упаковки состоит из нескольких файлов заголовков. Для любого преобразования требуется только один файл, но при необходимости для других преобразований можно включить дополнительные файлы. Таблица в `Marshaling Overview in C++` указывает, какой файл маршалирования должен быть добавлен для каждого преобразования.

### <a name="example"></a>Пример

В этом примере создается контекст для маршалирования из в `System::String` `const char *` тип переменной. Преобразованные данные не будут действительны после строки, которая удаляет контекст.

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
