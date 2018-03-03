---
title: "Класс CColorDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38fbca875847e557981c09dc418c8e0ef65bed6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccolordialog-class"></a>Класс CColorDialog
Позволяет включить диалоговое окно выбора цвета в приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Создает объект `CColorDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Отображает диалоговое окно «цвет» и позволяет пользователю сделать выбор.|  
|[CColorDialog::GetColor](#getcolor)|Возвращает **COLORREF** структуру, содержащую значения из выбранного цвета.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Извлекает пользовательских цветов, созданных пользователем.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Вызывает текущий цвет в указанный цвет.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|Переопределите, чтобы проверить введенные в диалоговом окне цвет.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|Структура, используемая для настройки параметров диалогового окна.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CColorDialog` объект — это диалоговое окно со списком цветов, которые определены для отображения системы. Пользователю можно выбрать или создать определенным цветом в списке, которой затем сообщается обратно в приложение при завершении работы в диалоговом окне.  
  
 Для создания `CColorDialog` объекта, используйте предоставленный конструктор или наследовать новый класс и использовать собственный пользовательский конструктор.  
  
 После создания диалоговом окне можно задать или изменить значения в [m_cc](#m_cc) структуры для инициализации значений элементов управления в диалоговое окно «». `m_cc` Структуры имеет тип [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 После инициализации элементов управления в диалоговое окно «», вызовите метод `DoModal` функции-члена для отображения диалогового окна и разрешить пользователю выбрать цвет. `DoModal`Возвращает пользователя Выбор любого ОК диалоговое окно «» ( **IDOK**) или "Отмена" ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CColorDialog`в функции-члены для извлечения информации, введенное пользователем.  
  
 Можно использовать окна [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и Дополнительные сведения об ошибке.  
  
 `CColorDialog`использует COMMDLG. Файл DLL, который поставляется вместе с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CColorDialog`, укажите шаблон настраиваемое диалоговое окно и добавить схему сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любой необработанных сообщений должны передаваться в базовом классе.  
  
 Функция-ловушка Настройка не требуется.  
  
> [!NOTE]
>  В некоторых установках `CColorDialog` объект не будет отображать с серым фоном, если используется платформа вносить другие `CDialog` объекты серого.  
  
 Дополнительные сведения об использовании `CColorDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>CColorDialog::CColorDialog  
 Создает объект `CColorDialog`.  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *clrInit*  
 Выбор цвета по умолчанию. Если значение не указано, значение по умолчанию — RGB(0,0,0) (черный).  
  
 `dwFlags`  
 Набор флагов, позволяющих настраивать функции и внешний вид диалогового окна. Дополнительные сведения см. в разделе [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) структуры в Windows SDK.  
  
 `pParentWnd`  
 Указатель на диалоговое окно родительского или владельца.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CColorDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна Windows общие цвета и разрешить пользователю выбрать цвет.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** — константы, которые указывают, является ли пользователь выбрал кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные параметры диалогового окна цвет, задав члены [m_cc](#m_cc) структуры, это следует сделать до вызова метода `DoModal` , но после создания объекта диалогового окна.  
  
 После вызова метода `DoModal`, можно вызывать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="getcolor"></a>CColorDialog::GetColor  
 Эта функция вызывается после вызова метода `DoModal` для извлечения сведений о выбранный пользователем цвет.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) значение, которое содержит сведения для цвета, выбранного в диалоговом окне цветов RGB.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors  
 `CColorDialog`объекты позволяют пользователю, помимо выбора цвета, для определения пользовательских до 16 цветов.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на массив 16 цветовых значений RGB, хранящая пользовательские цвета, созданных пользователем.  
  
### <a name="remarks"></a>Примечания  
 `GetSavedCustomColors` Функция-член предоставляет доступ к эти цвета. Эти цвета можно получить после [DoModal](#domodal) возвращает **IDOK**.  
  
 Каждый из 16 значений RGB в возвращаемый массив инициализируется RGB(255,255,255) (белый). Пользовательские цвета, выбранного пользователем, сохраняются только между вызовами поле диалогового окна в приложении. Если вы хотите сохранить эти цвета между вызовами приложения, необходимо сохранить их в других целях, таких как в инициализации (. Файл INI-ФАЙЛЕ).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>CColorDialog::m_cc  
 Структура типа [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), члены которого хранения характеристики и значения диалогового окна.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CColorDialog` объекта, можно использовать `m_cc` для задания различных аспектов диалоговым окном перед вызовом [DoModal](#domodal) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>CColorDialog::OnColorOK  
 Переопределите, чтобы проверить введенные в диалоговом окне цвет.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если диалоговое окно не должно быть отброшено; в противном случае значение 0, чтобы принять цвет, который был введен.  
  
### <a name="remarks"></a>Примечания  
 Эту функцию можно переопределите только в том случае, если вы хотите предоставить пользовательскую проверку цвета, выбранного пользователем в диалоговом окне цветов.  
  
 Пользователь может выбрать цвет одним из следующих двух способов:  
  
-   Щелкните нужный цвет в палитре цветов. Затем значения выбранного цвета RGB отражаются в соответствующих полях редактирования RGB.  
  
-   Ввод значения в значение RGB с полями ввода  
  
 Переопределение `OnColorOK` позволяет отклонять цвет, пользователь вводит часто используемое диалоговое окно цвет для какой-либо причине конкретного приложения.  
  
 Как правило необязательно использовать эту функцию, так как платформа выполняет проверку по умолчанию цвета и отображает окно сообщения, если введен недопустимый цвет.  
  
 Можно вызвать [SetCurrentColor](#setcurrentcolor) изнутри `OnColorOK` для принудительного выбора цвета. Один раз `OnColorOK` произошло (то есть пользователь нажимает кнопку **ОК** принять изменение цвета), можно вызвать [GetColor](#getcolor) для получения значения нового цвета RGB.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor  
 Эта функция вызывается после вызова метода `DoModal` для принудительного текущий цвет в значение цвета, указанные в `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Параметры  
 `clr`  
 Значение цвета RGB.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается из обработчика сообщений или `OnColorOK`. Диалоговое окно будет автоматически обновляться на основе значения из выбранных пользователем `clr` параметра.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [Пример MFC ФУНКЦИЙ](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

