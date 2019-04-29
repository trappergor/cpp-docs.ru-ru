---
title: Перечисление UICheckState
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 1411e9b7cb088c063e17cc7c59871e5f0b83ad9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309802"
---
# <a name="uicheckstate-enumeration"></a>Перечисление UICheckState

Описывает состояние проверки элемента интерфейса пользователя для команды.

### <a name="syntax"></a>Синтаксис

```
public enum class
{
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]
   Unchecked,
   Checked,
   Indeterminate
};
```

### <a name="remarks"></a>Примечания

[ICommandUI::Check](icommandui-interface.md#check) использует эти значения, описывающие состояние элемента интерфейса пользователя.
Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определенных в сборке atlmfc\lib\mfcmifc80.dll)
