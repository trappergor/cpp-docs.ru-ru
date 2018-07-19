---
title: Макросы и функции для управления библиотеки DLL | Документация Майкрософт
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee79ccad55d2fd360166b9d693f3d4757fe2049f
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339232"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Макросы и функции для управления библиотеки DLL

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Экспортирует классы.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Защитите экспортированной функции в DLL.|
|[AfxOleInitModule](#afxoleinitmodule)|Обеспечивает поддержку OLE из обычной библиотеки DLL MFC, динамически компонуемые с MFC.|
|[AfxNetInitModule](#afxnetinitmodule)|Обеспечивает поддержку сокетов MFC с обычной библиотеки DLL MFC, динамически компонуемые с MFC.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Возвращает текущее состояние флага состояние-module.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Задает состояние модуля перед инициализацией и/или для восстановления предыдущего состояния модуля после очистки.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|Инициализирует библиотеку DLL.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|Задайте флаг состояния каждого модуля, который влияет на поведение WinSxS MFC.|
|[Функцию AfxTermExtensionModule]()#afxtermextensionmodule)|Позволяет MFC для очистки библиотеки DLL расширения MFC после отсоединения всех процессов из библиотеки DLL.|


## <a name="afx_ext_class"></a>  AFX_EXT_CLASS
[Библиотеки DLL расширений MFC](../../build/extension-dlls.md) использовать макросы AFX_EXT_CLASS процедура экспорта классов; исполняемые файлы, связанные библиотеки DLL расширения MFC использовать макрос процедура импорта классов.  
   
### <a name="remarks"></a>Примечания  
 С помощью макроса AFX_EXT_CLASS же файлы заголовка, которые используются для создания библиотеки DLL расширения MFC можно использовать с исполняемыми файлами, связанных с библиотекой DLL.  
  
 В файле заголовка для библиотеки DLL добавьте ключевое слово AFX_EXT_CLASS объявление класса следующим образом:  
  
```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
``` 
  
 Дополнительные сведения см. в разделе [экспорта и импорта с использованием AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md).  
   
### <a name="requirements"></a>Требования  
 Заголовок: **afxv_** dll.h  
   
## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE
Вызовите этот макрос для защиты экспортированной функции в DLL.  
   
### <a name="syntax"></a>Синтаксис    
```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )  
```
### <a name="parameters"></a>Параметры  
 *pModuleState*  
 Указатель на `AFX_MODULE_STATE` структуры.  
   
### <a name="remarks"></a>Примечания  
 При вызове этот макрос *pModuleState* — эффективный модуля состояния в течение немедленно, содержащий область. При уходе из области, предыдущее состояние действующие модуль будет автоматически восстановлено.    
 `AFX_MODULE_STATE` Структура содержит глобальные данные этого модуля, то есть часть состояния модуля, передаче или извлекается.    
 По умолчанию MFC использует дескриптор ресурсов основного приложения для загрузки шаблона ресурсов. При наличии экспортированной функции в DLL, например, запускает диалоговое окно в библиотеке DLL, этот шаблон хранится в модуле библиотеки DLL. Необходимо переключать состояние модуля для правильного дескриптор для использования. Это можно сделать, добавив следующий код в начало функции:    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 Это меняет местами текущее состояние модуля с состоянием, возвращенные [AfxGetStaticModuleState](#afxgetstaticmodulestate) до конца текущей области.    
 Дополнительные сведения о состояния модулей и MFC, см. в разделе «Управление данными о состоянии модулей MFC» в [создание новых документов, Windows и представления](../creating-new-documents-windows-and-views.md) и [технические 58 Примечание](../tn058-mfc-module-state-implementation.md).    
> [!NOTE]
>  Когда MFC создает контекст активации для сборки, он использует [AfxWinInit](#afxwininit) для создания контекста и `AFX_MANAGE_STATE` включать и отключать его. Обратите внимание, что `AFX_MANAGE_STATE` включена для статические библиотеки MFC, а также библиотеки DLL MFC, чтобы разрешить MFC код, выполняемый в контексте правильной активации выбранного библиотекой пользователя. Дополнительные сведения см. в разделе [поддержка контекстов активации в состоянии модуля MFC](../support-for-activation-contexts-in-the-mfc-module-state.md).     
### <a name="requirements"></a>Требования  
 **Заголовок:** afxstat_.h  
   
### <a name="see-also"></a>См. также  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule
Для поддержки OLE из обычной библиотеки DLL MFC, динамически компонуемые с MFC, эта функция библиотеки регулярных DLL MFC `CWinApp::InitInstance` функцию для инициализации OLE библиотеки DLL MFC.  
   
### <a name="syntax"></a>Синтаксис    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>Примечания  
 MFC Библиотеки OLE является расширением MFC DLL. в порядке для библиотеки DLL расширения MFC в `CDynLinkLibrary` цепочки, его необходимо создать `CDynLinkLibrary` объект в контексте каждого модуля, он будет использоваться. `AfxOleInitModule` Создает `CDynLinkLibrary` объекта в контексте библиотеки регулярных DLL MFC, таким образом, чтобы он получает встроены в `CDynLinkLibrary` объект цепочки обычной библиотеки DLL MFC.  
  
 Если вы создаете управления OLE и используете `COleControlModule`, не следует вызывать `AfxOleInitModule` поскольку `InitInstance` функция-член для `COleControlModule` вызовы `AfxOleInitModule`.  
   
### <a name="requirements"></a>Требования  
 **Заголовок**: < afxdll_.h >  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>  AfxNetInitModule
Для сокетов MFC поддерживает регулярных DLL MFC, динамически компонуемые с MFC, добавьте вызов данной функции в библиотеке регулярных DLL MFC `CWinApp::InitInstance` функцию для инициализации библиотеки DLL MFC сокетов.  
   
### <a name="syntax"></a>Синтаксис    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>Примечания  
 Библиотеки DLL MFC сокетов является расширением MFC DLL. в порядке для библиотеки DLL расширения MFC в `CDynLinkLibrary` цепочки, его необходимо создать `CDynLinkLibrary` объект в контексте каждого модуля, он будет использоваться. `AfxNetInitModule` Создает `CDynLinkLibrary` объекта в контексте библиотеки регулярных DLL MFC, таким образом, чтобы он получает встроены в `CDynLinkLibrary` объект цепочки обычной библиотеки DLL MFC.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** < afxdll_.h >  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx
Эту функцию можно используйте для получения текущего состояния состояние флага-module, который влияет на поведение WinSxS MFC.  
   
### <a name="syntax"></a>Синтаксис    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>Возвращаемое значение  
 Модуль состояния текущее значение флага.  
   
### <a name="remarks"></a>Примечания  
 Когда этот флаг имеет значение (по умолчанию), и поток входит в модуль MFC (см. в разделе [AFX_MANAGE_STATE](#afx_manage_state)), активируется контекст модуля.  
  
 Если флаг не установлен, контекст модуля на запись не включен.  
  
 Контекст модуля определяется на основе его манифест, обычно внедрены в ресурсов модуля.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxcomctl32.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [Управление данными состояния модулей MFC](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState
Вызывайте эту функцию для задания состояния модуля перед инициализацией и/или для восстановления предыдущего состояния модуля после очистки.  
   
### <a name="syntax"></a>Синтаксис    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `AFX_MODULE_STATE` структуры.  
   
### <a name="remarks"></a>Примечания  
 `AFX_MODULE_STATE` Структура содержит глобальные данные этого модуля, то есть часть состояния модуля, передаче или извлекается.  
  
 По умолчанию MFC использует дескриптор ресурсов основного приложения для загрузки шаблона ресурсов. При наличии экспортированной функции в DLL, например, запускает диалоговое окно в библиотеке DLL, этот шаблон хранится в модуле библиотеки DLL. Необходимо переключать состояние модуля для правильного дескриптор для использования. Это можно сделать, добавив следующий код в начало функции:  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 Это меняет местами текущее состояние модуля с состоянием, возвращенные `AfxGetStaticModuleState` до конца текущей области.  
  
 Дополнительные сведения о состояния модулей и MFC, см. в разделе «Управление данными о состоянии модулей MFC» в [создание новых документов, Windows и представления](../creating-new-documents-windows-and-views.md) и [технические 58 Примечание](../tn058-mfc-module-state-implementation.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a> AfxInitExtensionModule
Вызовите эту функцию в MFC библиотеки DLL расширения `DllMain` для инициализации библиотеки DLL.  
   
### <a name="syntax"></a>Синтаксис    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>Параметры  
 *state*  
 Ссылку на [структура AFX_EXTENSION_MODULE](afx-extension-module-structure.md) структуру, которая будет содержать состояние модуля DLL расширения MFC после инициализации. Состояние включает копию объекты класса среды выполнения, для инициализации библиотеки DLL расширения MFC как часть конструкции обычный статический объект, перед выполнением `DllMain` вводится.  
  
 *hModule*  
 Дескриптор модуля DLL расширения MFC.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если библиотека DLL расширения MFC инициализирован успешно; в противном случае — значение FALSE.  
   
### <a name="remarks"></a>Примечания  
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

```
  
 `AfxInitExtensionModule` Создает копию библиотеки DLL HMODULE и захватывает классов среды выполнения DLL (`CRuntimeClass` структур) а также производства объектов (`COleObjectFactory` объектов) для использования более поздние версии `CDynLinkLibrary` создается объект.    
 Расширения MFC DLL-библиотеки нужно сделать две вещи в свои `DllMain` функции:    
-   Вызовите [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) и проверяйте возвращаемое значение.   
-   Создание `CDynLinkLibrary` объекта, если библиотека DLL будет экспортироваться [структура CRuntimeClass](cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы.    
 Можно вызвать `AfxTermExtensionModule` для очистки библиотеки DLL расширения MFC, при каждом процессе отсоединяется от библиотеки DLL расширения MFC (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате использования `AfxFreeLibrary` вызова).     

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdll_.h     

### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Функцию AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx
Эту функцию можно используйте для установки состояния флага-module, влияющий на поведение WinSxS MFC.  
   
### <a name="syntax"></a>Синтаксис  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>Параметры  
 *bSet*  
 Новое значение флага состояния модуля.  
   
### <a name="remarks"></a>Примечания  
 Когда этот флаг имеет значение (по умолчанию), и поток входит в модуль MFC (см. в разделе [AFX_MANAGE_STATE](#afx_manage_state)), активируется контекст модуля.    
 Если флаг не установлен, контекст модуля на запись не включен.    
 Контекст модуля определяется на основе его манифест, обычно внедрены в ресурсов модуля.  
   
### <a name="example"></a>Пример  
 ```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
```
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxcomctl32.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxGetAmbientActCtx](#afxgetambientactctx)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [Управление данными состояния модулей MFC](../managing-the-state-data-of-mfc-modules.md) 

## <a name="afxtermextensionmodule"></a>  Функцию AfxTermExtensionModule

Вызывайте эту функцию, чтобы разрешить MFC очистки библиотеки DLL расширения MFC после отсоединения всех процессов из библиотеки DLL (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате использования `AfxFreeLibrary` вызова).  
   
### <a name="syntax"></a>Синтаксис  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>Параметры  
 *state*  
 Ссылку на [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) структуру, содержащую состояние модуля DLL расширения MFC.  
  
 *Шар*  
 Если значение TRUE, очистка всех модулей библиотеки DLL расширения MFC. В противном случае — Очистка только текущего модуля DLL.  
   
### <a name="remarks"></a>Примечания  
 `AfxTermExtensionModule` удалит все локальном хранилище, подключенном к модуля и удалить все записи из кэша сопоставлений сообщений. Пример:  
  
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
  
 Если приложение загружает и освобождает библиотек DLL расширений MFC, динамически, необходимо вызвать `AfxTermExtensionModule`. Так как большинство расширения MFC, библиотеки DLL не загружаются динамически (как правило, они связаны с помощью свои библиотеки импорта), вызов `AfxTermExtensionModule` обычно нет необходимости.  
  
 Библиотеки DLL расширения MFC, необходимые для вызова [AfxInitExtensionModule](#afxinitextensionmodule) в их `DllMain`. Если библиотека DLL будет экспортироваться [CRuntimeClass](cruntimeclass-structure.md) объектов или имеет свои собственные пользовательские ресурсы, необходимо также создать `CDynLinkLibrary` объекта в `DllMain`.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdll_.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




