---
title: оператор Type^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: 180efcac76b7f51291a47ee68508e7444a6c069c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161814"
---
# <a name="operator-type"></a>оператор Type^

Включает преобразование из [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) в `Platform::Type`.

## <a name="syntax"></a>Синтаксис

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `Platform::Type` при получении [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

### <a name="remarks"></a>Примечания

`TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе. [Platform::Type](../cppcx/platform-type-class.md) используется только в C++ и не передается через двоичный интерфейс приложений (ABI). Ниже представлен один из способов использования `TypeName`в функции [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) .

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Пример

В следующем примере показано преобразование из `TypeName` в `Type`и наоборот.

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Проект программы .NET framework `TypeName` как <xref:System.Type>

### <a name="requirements"></a>Требования

## <a name="see-also"></a>См. также

[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Класс Platform::Type](../cppcx/platform-type-class.md)
