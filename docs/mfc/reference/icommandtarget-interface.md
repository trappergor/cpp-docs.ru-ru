---
title: Интерфейс ICommandTarget | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95faae4de2e9fa756a4f69f231839e19019e08fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436810"
---
# <a name="icommandtarget-interface"></a>Интерфейс ICommandTarget

Предоставляет пользовательский элемент управления с помощью интерфейса для получения команд из исходного объекта команды.

## <a name="syntax"></a>Синтаксис

```
interface class ICommandTarget
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ICommandTarget::Initialize](#initialize)|Инициализирует целевой объект команды.|

## <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды сообщения пользовательского интерфейса для пользовательского элемента управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, вы предоставляете ссылку на пользовательский элемент управления [ICommandSource](../../mfc/reference/icommandsource-interface.md) объекта.

См. в разделе [как: Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h (определенных в сборке atlmfc\lib\mfcmifc80.dll)

##  <a name="initialize"></a> ICommandTarget::Initialize

Инициализирует целевой объект команды.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Параметры

*cmdSource*<br/>
Дескриптор объект источника команды.

### <a name="remarks"></a>Примечания

При размещении пользовательского элемента управления в представления MFC, CWinFormsView направляет команды и сообщения пользовательского интерфейса команды обновления в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC.

Этот метод инициализирует целевого объекта команды и связывает его с cmdSource объекта источника указанную команду. Он должен вызываться в реализацию класса пользовательского элемента управления. При инициализации необходимо зарегистрировать обработчики команд с исходным объектом команды путем вызова ICommandSource::AddCommandHandler в реализации Initialize. См. в разделе Практическое: Добавление маршрутизации команд к элементу управления Windows Forms, пример демонстрирует использование инициализации для этого.

## <a name="see-also"></a>См. также

[Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[Интерфейс ICommandSource](../../mfc/reference/icommandsource-interface.md)



