---
title: оператор Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 7480df474086d78e28d235cc89b05094c648d28b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415179"
---
# <a name="operator-windowsuixamlinteroptypename"></a>оператор Windows::UI::Xaml::Interop::TypeName

Включает преобразование из `Platform::Type` в [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

## <a name="syntax"></a>Синтаксис

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) при получении `Platform::Type^`.

### <a name="remarks"></a>Примечания

`TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе. [Platform::Type](../cppcx/platform-type-class.md) используется только в C++ и не передается через двоичный интерфейс приложений (ABI). Ниже представлен один из способов использования `TypeName`в функции [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) .

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Пример

В следующем примере показано преобразование из `TypeName` в `Type`и наоборот.

```

// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

.NET Framework программирует `TypeName` проекта как [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).

### <a name="requirements"></a>Требования

## <a name="see-also"></a>См. также

[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Класс Platform::Type](../cppcx/platform-type-class.md)