---
title: "Макросы и функции для управления DLL | Документы Microsoft"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7807d112b45b7316b630522ab7f896201d53ff2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="macros-and-functions-for-managing-dlls"></a>Макросы и функции для управления библиотеки DLL

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|Экспортирует классы.|
|[AFX_MANAGE_STATE](#afx_manage_state)|Защитите экспортированной функции в DLL.|
|[AfxOleInitModule](#afxoleinitmodule)|Обеспечивает поддержку OLE из обычной MFC DLL, динамически компонуемые с MFC.|
|[AfxNetInitModule](#afxnetinitmodule)|Обеспечивает поддержку сокетов MFC с обычной MFC DLL, динамически компонуемые с MFC.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|Возвращает текущее состояние флага состояния-module.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|Задает состояние модуля до инициализации и (или) для восстановления предыдущего состояния модуля после очистки.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|Инициализирует библиотеку DLL.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|Установите флаг состояния-модуль, который влияет на поведение WinSxS MFC.|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|Используется в MFC для очистки библиотеки DLL расширения MFC после отсоединения всех процессов из библиотеки DLL.|


## <a name="afx_ext_class"></a>AFX_EXT_CLASS
[Библиотека DLL-расширения MFC](../../build/extension-dlls.md) используйте макрос **AFX_EXT_CLASS** Экспорт классов; исполняемые файлы, связанные с DLL расширений MFC использовать макрос для импорта классы.  
   
### <a name="remarks"></a>Примечания  
 С **AFX_EXT_CLASS** макрос, можно использовать файлы, используемые для создания библиотеки DLL расширения MFC с исполняемыми файлами, связан с библиотекой DLL и тот же заголовок.  
  
 Добавьте в файл заголовка для библиотеки DLL, **AFX_EXT_CLASS** ключевое слово в объявление класса следующим образом:  
  
```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
``` 
  
 Дополнительные сведения см. в разделе [экспорта и импорта с использованием AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md).  
   
### <a name="requirements"></a>Требования  
 Заголовок: **afxv_**dll.h  
   
## <a name="afx_manage_state"></a>AFX_MANAGE_STATE
Вызов этого макроса, чтобы защитить экспортированной функции в DLL.  
   
### <a name="syntax"></a>Синтаксис    
```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )  
```
### <a name="parameters"></a>Параметры  
 `pModuleState`  
 Указатель на `AFX_MODULE_STATE` структуры.  
   
### <a name="remarks"></a>Примечания  
 При вызове этого макроса `pModuleState` действующие модуля состояния для оставшихся непосредственные содержащего области. После закрывать область, предыдущее состояние действующие модуль будет автоматически восстановлена.    
 `AFX_MODULE_STATE` Структура содержит глобальные данные этого модуля, то есть часть состояния модуля, который является передаются или выводятся.    
 По умолчанию MFC использует дескриптор ресурса основного приложения для загрузки шаблона ресурсов. При наличии экспортированной функции в DLL, например, диалоговое окно «» в библиотеке DLL, этот шаблон фактически хранится в модуле библиотеки DLL. Если требуется переключить состояние модуля для правильного дескриптор для использования. Это можно сделать, добавив следующий код в начало функции:    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 Это меняет текущего состояния модуля с состоянием, возвращенные [AfxGetStaticModuleState](#afxgetstaticmodulestate) до конца текущей области.    
 Дополнительные сведения о состояния модулей и MFC см. в разделе «Управление данными о состоянии модулей MFC» в [создание новых документов, окон и представлений](../creating-new-documents-windows-and-views.md) и [Техническая заметка 58](../tn058-mfc-module-state-implementation.md).    
> [!NOTE]
>  Когда MFC создает контекст активации для сборки, он использует [AfxWinInit](#afxwininit) для создания контекста и `AFX_MANAGE_STATE` активации и деактивации его. Обратите внимание, что `AFX_MANAGE_STATE` включена для статические библиотеки MFC, а также библиотеки DLL MFC, чтобы разрешить код MFC в контексте правильной активации, выбранного пользователем библиотеки DLL. Дополнительные сведения см. в разделе [поддержка контекстов активации в состоянии модуля MFC](../support-for-activation-contexts-in-the-mfc-module-state.md).     
### <a name="requirements"></a>Требования  
 **Заголовок:** afxstat_.h  
   
### <a name="see-also"></a>См. также  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/>AfxOleInitModule
Для поддержки OLE из обычной MFC DLL, динамически компонуемые с MFC, эта функция вызывается в библиотеке регулярных DLL MFC `CWinApp::InitInstance` функцию для инициализации OLE библиотеки DLL MFC.  
   
### <a name="syntax"></a>Синтаксис    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>Примечания  
 MFC Библиотеки OLE является расширением MFC DLL. Чтобы библиотеки DLL расширения MFC в **CDynLinkLibrary** цепочки, его необходимо создать **CDynLinkLibrary** объект в контексте каждого модуля, он будет использоваться. `AfxOleInitModule`Создает **CDynLinkLibrary** объекта в контексте вашей регулярных DLL MFC, чтобы он получает встроены в **CDynLinkLibrary** объекта цепочку регулярных DLL MFC.  
  
 Если вы создаете элемента управления OLE и используете `COleControlModule`, не следует вызывать **AfxOleInitModule** из-за `InitInstance` функции-члена для `COleControlModule` вызовы `AfxOleInitModule`.  
   
### <a name="requirements"></a>Требования  
 **Заголовок**: < afxdll_.h >  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>AfxNetInitModule
Для сокетов MFC поддерживает из обычной MFC DLL, динамически компонуемые с MFC, добавьте вызов этой функции в библиотеке регулярных DLL MFC **CWinApp::InitInstance** функцию для инициализации библиотеки DLL MFC сокетов.  
   
### <a name="syntax"></a>Синтаксис    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>Примечания  
 Сокеты DLL MFC — это расширение MFC DLL. Чтобы библиотеки DLL расширения MFC в **CDynLinkLibrary** цепочки, его необходимо создать **CDynLinkLibrary** объект в контексте каждого модуля, он будет использоваться. `AfxNetInitModule`Создает **CDynLinkLibrary** объекта в контексте вашей регулярных DLL MFC, чтобы он получает встроены в **CDynLinkLibrary** объекта цепочку регулярных DLL MFC.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** < afxdll_.h >  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a>AfxGetAmbientActCtx
Эту функцию можно используйте для получения текущего состояния флаг состояния каждого модуля, который влияет на поведение WinSxS MFC.  
   
### <a name="syntax"></a>Синтаксис    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>Возвращаемое значение  
 Модуль состояния текущее значение флага.  
   
### <a name="remarks"></a>Примечания  
 Если флаг устанавливается (это значение по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE](#afx_manage_state)), активируется контекст модуля.  
  
 Если флаг не установлен, контекст модуля не активировано на запись.  
  
 Контекст модуля определяется его манифест, обычно внедряются в ресурсы модуля.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxcomctl32.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [Управление данными состояния модулей MFC](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a>AfxGetStaticModuleState
Вызывайте эту функцию для задания состояния модуля до инициализации и (или) для восстановления предыдущего состояния модуля после очистки.  
   
### <a name="syntax"></a>Синтаксис    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `AFX_MODULE_STATE` структуры.  
   
### <a name="remarks"></a>Примечания  
 `AFX_MODULE_STATE` Структура содержит глобальные данные этого модуля, то есть часть состояния модуля, который является передаются или выводятся.  
  
 По умолчанию MFC использует дескриптор ресурса основного приложения для загрузки шаблона ресурсов. При наличии экспортированной функции в DLL, например, диалоговое окно «» в библиотеке DLL, этот шаблон фактически хранится в модуле библиотеки DLL. Если требуется переключить состояние модуля для правильного дескриптор для использования. Это можно сделать, добавив следующий код в начало функции:  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 Это меняет текущего состояния модуля с состоянием, возвращенные `AfxGetStaticModuleState` до конца текущей области.  
  
 Дополнительные сведения о состояния модулей и MFC см. в разделе «Управление данными о состоянии модулей MFC» в [создание новых документов, окон и представлений](../creating-new-documents-windows-and-views.md) и [Техническая заметка 58](../tn058-mfc-module-state-implementation.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule
Вызовите эту функцию в DLL расширений MFC `DllMain` для инициализации библиотеки DLL.  
   
### <a name="syntax"></a>Синтаксис    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>Параметры  
 `state`  
 Ссылку на [структура AFX_EXTENSION_MODULE](afx-extension-module-structure.md) структура, которая будет содержать состояния модуля MFC DLL расширения после инициализации. Состояние включает в себя копирование объектов классов среды выполнения, которые инициализированы с DLL расширений MFC как часть построения обычного статического объекта перед выполнением `DllMain` вводится.  
  
 `hModule`  
 Дескриптор модуля MFC DLL расширения.  
   
### <a name="return-value"></a>Возвращаемое значение  
 **Значение TRUE,** если библиотеки DLL расширения MFC успешно инициализирован; в противном случае — **FALSE**.  
   
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
  
 `AfxInitExtensionModule`Создает копию библиотеки DLL **HMODULE** и записывает классов среды выполнения DLL (`CRuntimeClass` структуры) а также производства объектов (`COleObjectFactory` объектов) для использования более поздние версии **CDynLinkLibrary**создан объект.    
 Расширения MFC библиотеки DLL, необходимо выполнить два действия в их `DllMain` функции:    
-   Вызовите [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) и проверяйте возвращаемое значение.   
-   Создание **CDynLinkLibrary** объекта, если библиотека DLL будет экспортироваться [структуры CRuntimeClass](cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы.    
 Можно вызвать `AfxTermExtensionModule` для очистки библиотеки DLL расширения MFC, после отсоединения всех процессов из библиотеки DLL расширения MFC (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате использования `AfxFreeLibrary` вызова).     

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdll_.h     

### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>AfxSetAmbientActCtx
Эта функция используется для установки флага состояния-module, который влияет на поведение WinSxS MFC.  
   
### <a name="syntax"></a>Синтаксис  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>Параметры  
 `bSet`  
 Новое значение флага состояния модуля.  
   
### <a name="remarks"></a>Примечания  
 Если флаг устанавливается (это значение по умолчанию) и поток входит в модуль MFC (см. [AFX_MANAGE_STATE](#afx_manage_state)), активируется контекст модуля.    
 Если флаг не установлен, контекст модуля не активировано на запись.    
 Контекст модуля определяется его манифест, обычно внедряются в ресурсы модуля.  
   
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

## <a name="afxtermextensionmodule"></a>AfxTermExtensionModule

Эта функция позволяет MFC для очистки библиотеки DLL расширения MFC после отсоединения всех процессов из библиотеки DLL (что происходит при завершении процесса или при выгрузке библиотеки DLL в результате использования `AfxFreeLibrary` вызова).  
   
### <a name="syntax"></a>Синтаксис  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>Параметры  
 `state`  
 Ссылку на [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) структура, содержащая состояние модуль DLL расширения MFC.  
  
 *Шар*  
 Если **TRUE**, очистку всех модулей DLL расширения MFC. В противном случае — очистки в текущем модуле библиотеки DLL.  
   
### <a name="remarks"></a>Примечания  
 `AfxTermExtensionModule`будет удалено любого локального хранилища, присоединенного к модулю, а также удалить все записи из кэша карты сообщений. Пример:  
  
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
  
 Если приложение загружает и динамически освобождает библиотека DLL-расширения MFC, необходимо вызвать `AfxTermExtensionModule`. Поскольку большинство расширения MFC, библиотеки DLL не загружаются динамически (как правило, они связаны через их библиотеки импорта), вызов `AfxTermExtensionModule` обычно нет необходимости.  
  
 Расширения MFC DLL-библиотеки нужно вызывать [AfxInitExtensionModule](#afxinitextensionmodule) в их `DllMain`. Если библиотека DLL будет экспортировать [CRuntimeClass](cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы, необходимо создать **CDynLinkLibrary** объекта в `DllMain`.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdll_.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




