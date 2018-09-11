---
title: оператор Windows::UI::Xaml::Interop::TypeName | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 262fb9d08da72201db041eff1a510a598851e3e2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105969"
---
# <a name="operator-windowsuixamlinteroptypename"></a>оператор Windows::UI::Xaml::Interop::TypeName

Включает преобразование из `Platform::Type` для [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).

## <a name="syntax"></a>Синтаксис

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) при получении `Platform::Type^`.

### <a name="remarks"></a>Примечания

`TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе. [Platform::Type](../cppcx/platform-type-class.md) используется только в C++ и не передается через двоичный интерфейс приложений (ABI). Вот один из способов использования `TypeName`в [Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx) функции:

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

[Оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Класс Platform::Type](../cppcx/platform-type-class.md)