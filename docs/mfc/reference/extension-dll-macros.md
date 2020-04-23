---
title: Макрос и функции для управления DLL
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: 42a08ff2e806acae6713c9df3fe170f7e89f05af
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751597"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Макрос и функции для управления DLL

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)|Классы экспорта.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Защитите экспортируемую функцию в DLL.|
|[AfxOleInitModule](#afxoleinitmodule)|Предоставляет поддержку OLE от регулярного MFC DLL, который динамически связан с MFC.|
|[AfxNetInitModule](#afxnetinitmodule)|Предоставляет поддержку MFC Sockets от регулярного MFC DLL, который динамически связан с MFC.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Получает текущее состояние флага состояния модуля.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Устанавливает состояние модуля до инициализации и/или восстанавливает предыдущее состояние модуля после очистки.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|Инициализирует DLL.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|установить флаг состояния для модуля, который влияет на поведение InSxS MFC.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|Позволяет MFC очистить расширение MFC DLL, когда каждый процесс отделяется от DLL.|

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a>Afx_ext_class

[DLL расширения MFC](../../build/extension-dlls.md) используют макро-AFX_EXT_CLASS для экспорта классов; исполнители, которые ссылаются на расширение MFC DLL, используют макрос для классов импорта.

### <a name="remarks"></a>Remarks

С AFX_EXT_CLASS макроса, тот же файл заголовка (ы), используемый для создания DLL расширения MFC, может быть использован с исполнителями, которые ссылаются на DLL.

В файл заголовка для Вашего DLL добавьте ключевое слово AFX_EXT_CLASS в декларацию вашего класса следующим образом:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Для получения дополнительной информации см [AFX_EXT_CLASS.](../../build/exporting-and-importing-using-afx-ext-class.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxv_dll.h

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a>AFX_MANAGE_STATE

Вызовите этот макрос для защиты экспортируемой функции в DLL.

### <a name="syntax"></a>Синтаксис

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Параметры

*pModuleState*<br/>
Указатель на `AFX_MODULE_STATE` структуру.

### <a name="remarks"></a>Remarks

При вызове этого макроса *pModuleState* является эффективным состоянием модуля для оставшейся части непосредственно содержащей области. При выходе из области предыдущее состояние эффективного модуля будет автоматически восстановлено.
Структура `AFX_MODULE_STATE` содержит глобальные данные для модуля, то есть часть состояния модуля, которая выталкивается или высажается.

По умолчанию MFC использует ручку ресурсов основного приложения для загрузки шаблона ресурса. Если у вас есть экспортируемая функция в DLL, например, которая запускает диалоговое окно в DLL, этот шаблон фактически хранится в модуле DLL. Необходимо переключить состояние модуля для правильной ручки, которая будет использоваться. Вы можете сделать это, добавив следующий код к началу функции:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Это сменяет текущее состояние модуля с состоянием, возвращенным из [AfxGetStaticModuleState](#afxgetstaticmodulestate) до конца текущего объема.

Для получения дополнительной информации о состояниях модулей и MFC, [Creating New Documents, Windows, and Views](../creating-new-documents-windows-and-views.md) см. [Technical Note 58](../tn058-mfc-module-state-implementation.md)

> [!NOTE]
> Когда MFC создает контекст активации для сборки, он использует [AfxWinInit](application-information-and-management.md#afxwininit) для создания контекста и `AFX_MANAGE_STATE` активации и деактивации его. Обратите внимание `AFX_MANAGE_STATE` также, что включено для статических библиотек MFC, а также MFC DLLs, чтобы позволить коду MFC выполняться в надлежащем контексте активации, выбранном пользователем DLL. Для получения дополнительной информации смотрите [поддержка контекстов активации в состоянии модуля MFC](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxstat_.h

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>AfxOleInitModule

Для поддержки OLE от регулярного MFC DLL, который динамически связан с MFC, `CWinApp::InitInstance` позвоните по этой функции в вашей обычной функции MFC DLL, чтобы инициализировать MFC OLE DLL.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Remarks

MFC OLE DLL является расширением MFC DLL; для того, чтобы расширение MFC DLL `CDynLinkLibrary` попало в цепочку, оно должно создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxOleInitModule`создает `CDynLinkLibrary` объект в контексте вашего обычного MFC DLL, `CDynLinkLibrary` чтобы он попал в цепочку объектов обычного MFC DLL.

Если вы строите элемент управления `COleControlModule`OLE и `AfxOleInitModule` используете, вы не должны звонить, потому что функция `InitInstance` участника для `COleControlModule` вызовов. `AfxOleInitModule`

### <a name="requirements"></a>Требования

**Заголовок** \<: afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a>AfxNetInitМодуль

Для поддержки MFC Sockets от регулярного MFC DLL, который динамически связан с MFC, добавьте вызов к этой функции в `CWinApp::InitInstance` вашей обычной функции MFC DLL, чтобы инициализировать MFC Sockets DLL.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Remarks

MFC Sockets DLL является расширением MFC DLL; для того, чтобы расширение MFC DLL `CDynLinkLibrary` попало в цепочку, оно должно создать `CDynLinkLibrary` объект в контексте каждого модуля, который будет его использовать. `AfxNetInitModule`создает `CDynLinkLibrary` объект в контексте вашего обычного MFC DLL, `CDynLinkLibrary` чтобы он попал в цепочку объектов обычного MFC DLL.

### <a name="requirements"></a>Требования

**Заголовок:** \<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a>AfxGetAmbientActCtx

Используйте эту функцию, чтобы получить текущее состояние государственного флага для модуля, что влияет на поведение InSxS MFC.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Возвращаемое значение

Значение текущего флага состояния модуля.

### <a name="remarks"></a>Remarks

Когда флаг установлен (который является по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE),](#afx_manage_state)контекст модуля активируется.

Если флаг не установлен, контекст модуля не активируется при входе.

Контекст модуля определяется из его манифеста, обычно встроенного в ресурсы модуля.

### <a name="requirements"></a>Требования

**Заголовок:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState

Вызов этой функции для установки состояния модуля до инициализации и/или восстановления предыдущего состояния модуля после очистки.

### <a name="syntax"></a>Синтаксис

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `AFX_MODULE_STATE` структуру.

### <a name="remarks"></a>Remarks

Структура `AFX_MODULE_STATE` содержит глобальные данные для модуля, то есть часть состояния модуля, которая выталкивается или высажается.

По умолчанию MFC использует ручку ресурсов основного приложения для загрузки шаблона ресурса. Если у вас есть экспортируемая функция в DLL, например, которая запускает диалоговое окно в DLL, этот шаблон фактически хранится в модуле DLL. Необходимо переключить состояние модуля для правильной ручки, которая будет использоваться. Вы можете сделать это, добавив следующий код к началу функции:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

Это сменяет текущее состояние модуля с состоянием, возвращенным из `AfxGetStaticModuleState` до конца текущего объема.

Для получения дополнительной информации о состояниях модулей и MFC, [Creating New Documents, Windows, and Views](../creating-new-documents-windows-and-views.md) см. [Technical Note 58](../tn058-mfc-module-state-implementation.md)

### <a name="requirements"></a>Требования

**Заголовок:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

Вызовите эту функцию в расширении MFC DLL, `DllMain` чтобы инициализировать DLL.

### <a name="syntax"></a>Синтаксис

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Параметры

*state*<br/>
Ссылка на структуру [AFX_EXTENSION_MODULE,](afx-extension-module-structure.md) которая будет содержать состояние модуля DLL расширения MFC после инициализации. Состояние включает в себя копию объектов класса времени выполнения, которые были инициализированы DLL расширения MFC как часть нормальной конструкции статического объекта, выполненной до `DllMain` ввода.

*hModule*<br/>
Ручка модуля DLL расширения MFC.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если расширение MFC DLL успешно инициализировано; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

Пример:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule`делает копию HMODULE DLL и захватывает классы времени выполнения DLL`CRuntimeClass` (структуры), а также его`COleObjectFactory` объекты заводов (объектов) для использования позже, когда `CDynLinkLibrary` объект создан.
MFC расширение DLLs необходимо сделать `DllMain` две вещи в своей функции:

- Позвоните [в AfxInitExtensionModule](#afxinitextensionmodule) и проверьте значение возврата.

- Создайте `CDynLinkLibrary` объект, если DLL будет экспортировать [объекты CRuntimeClass Structure](cruntimeclass-structure.md) или имеет собственные пользовательские ресурсы.

Вы можете `AfxTermExtensionModule` позвонить, чтобы очистить расширение MFC DLL, когда каждый процесс отделяется от расширения MFC DLL (что происходит, когда `AfxFreeLibrary` процесс выходит, или когда DLL выгружается в результате вызова).

### <a name="requirements"></a>Требования

**Заголовок:** afxdll_.h

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a>AfxSetAmbientActCtx

Используйте эту функцию для установки флага состояния модуля, что влияет на поведение InSxS MFC.

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
Новое значение государственного флага модуля.

### <a name="remarks"></a>Remarks

Когда флаг установлен (который является по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE),](#afx_manage_state)контекст модуля активируется.
Если флаг не установлен, контекст модуля не активируется при входе.
Контекст модуля определяется из его манифеста, обычно встроенного в ресурсы модуля.

### <a name="example"></a>Пример

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a>AfxTermExtensionModule

Вызовите эту функцию, чтобы позволить MFC очистить расширение MFC DLL, когда каждый процесс отделяется от DLL (что происходит, `AfxFreeLibrary` когда процесс выходит, или когда DLL выгружается в результате вызова).

### <a name="syntax"></a>Синтаксис

```cpp
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>Параметры

*state*<br/>
Ссылка на [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) структуру, содержащую состояние модуля DLL расширения MFC.

*Мяч*<br/>
Если true, очистить все MFC расширение DLL модулей. В противном случае очистите только текущий модуль DLL.

### <a name="remarks"></a>Remarks

`AfxTermExtensionModule`удалит любое локальное хранилище, прикрепленное к модулю, и удалит все записи из кэша карты сообщений. Пример:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

Если ваше приложение загружается и динамически высвобождается расширениеМ MFC, обязательно позвоните. `AfxTermExtensionModule` Поскольку большинство DLL расширения MFC не загружаются динамически (обычно они `AfxTermExtensionModule` связаны через свои библиотеки импорта), вызов обычно не является необходимым.

MFC расширение DLLs необходимо позвонить [AfxInitExtensionModule](#afxinitextensionmodule) в их `DllMain`. Если DLL будет экспортировать объекты [CRuntimeClass](cruntimeclass-structure.md) или имеет собственные пользовательские `CDynLinkLibrary` ресурсы, необходимо также создать объект в. `DllMain`

### <a name="requirements"></a>Требования

**Заголовок:** afxdll_.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[Управление данными состояния модулей MFC](../managing-the-state-data-of-mfc-modules.md)<br/>
