---
title: оператор Type^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: fca53abb9dc17588695591d496b7db2a76e319f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553664"
---
# <a name="operator-type"></a>оператор Type^

Включает преобразование из [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) в `Platform::Type`.

## <a name="syntax"></a>Синтаксис

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `Platform::Type` при получении [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).

### <a name="remarks"></a>Примечания

`TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе. [Platform::Type](../cppcx/platform-type-class.md) используется только в C++ и не передается через двоичный интерфейс приложений (ABI). Ниже представлен один из способов использования `TypeName`в функции [Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx) .

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