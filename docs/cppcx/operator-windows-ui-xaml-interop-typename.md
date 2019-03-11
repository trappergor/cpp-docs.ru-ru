---
title: оператор Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 5acf17b7c87a71259dba6579d8ee69e0eea86fa5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738424"
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
