---
title: оператор Type ^ | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c0900da889e5bf9e8629349593ffce7740a1cf0
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="operator-type"></a>оператор Type^
Включает преобразование из [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) в `Platform::Type`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `Platform::Type` при получении [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
### <a name="remarks"></a>Примечания  
 `TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе. [Platform::Type](../cppcx/platform-type-class.md) используется только в C++ и не передается через двоичный интерфейс приложений (ABI). Ниже представлен один из способов использования `TypeName`в функции [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) .  
  
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
 .NET Framework программирует `TypeName` проекта как [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).  
  
### <a name="requirements"></a>Требования  
  
## <a name="see-also"></a>См. также  
 [оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Класс Platform::Type](../cppcx/platform-type-class.md)