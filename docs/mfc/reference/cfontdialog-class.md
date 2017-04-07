---
title: "Класс CFontDialog | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
dev_langs:
- C++
helpviewer_keywords:
- CFontDialog class
- dialog boxes, fonts
- fonts
- fonts, selecting
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6f277ba8fba72106918e03397f57726bd5beb0ff
ms.lasthandoff: 02/24/2017

---
# <a name="cfontdialog-class"></a>Класс CFontDialog
Позволяет включить диалоговое окно выбора шрифта в приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|Создает объект `CFontDialog`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|Отображает диалоговое окно и позволяет пользователю сделать выбор.|  
|[CFontDialog::GetCharFormat](#getcharformat)|Извлекает форматирования символов в выбранный шрифт.|  
|[CFontDialog::GetColor](#getcolor)|Возвращает цвет выбранного шрифта.|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Назначает характеристики выбранный шрифт для `LOGFONT` структуры.|  
|[CFontDialog::GetFaceName](#getfacename)|Возвращает имя шрифта выбранного шрифта.|  
|[CFontDialog::GetSize](#getsize)|Возвращает размер выбранного шрифта.|  
|[CFontDialog::GetStyleName](#getstylename)|Возвращает имя стиля выбранного шрифта.|  
|[CFontDialog::GetWeight](#getweight)|Возвращает вес выбранного шрифта.|  
|[CFontDialog::IsBold](#isbold)|Определяет, является ли шрифт полужирным.|  
|[CFontDialog::IsItalic](#isitalic)|Определяет, является ли шрифт курсивом.|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|Определяет, отображается ли шрифт зачеркивание.|  
|[CFontDialog::IsUnderline](#isunderline)|Определяет, является ли шрифт подчеркнутым.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|Структура, используемая для настройки `CFontDialog` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CFontDialog` объект — это диалоговое окно со списком шрифтов, установленных в системе. Пользователь может выбрать определенного шрифта из списка, и этот выбор затем отправляются обратно в приложение.  
  
 Для создания `CFontDialog` объекта, используйте предоставленный конструктор или получение нового подкласса и использовать собственный пользовательский конструктор.  
  
 Один раз `CFontDialog` объект был создан, можно использовать `m_cf` структуры для инициализации значения или состояния элементов управления в диалоговом окне. [M_cf](#m_cf) структуры имеет тип [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832). Дополнительные сведения о структуре см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 После инициализации объекта диалогового окна элементы управления, вызовите метод `DoModal` функции-члена для отображения диалогового окна и позволяет пользователю выбрать шрифт. `DoModal`Возвращает, выбрал ли пользователь ОК ( **IDOK**) или Отмена ( **IDCANCEL**) кнопки.  
  
 Если `DoModal` возвращает **IDOK**, можно использовать один из `CFontDialog`функции-члены для извлечения информации, введенное пользователем.  
  
 Можно использовать окна [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функции, чтобы определить, произошла ли ошибка во время инициализации диалогового окна и для получения дополнительных сведений об ошибке. Дополнительные сведения об этой функции см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog`зависит от COMMDLG. DLL-файл, поставляемый с Windows версии 3.1 и более поздней версии.  
  
 Чтобы настроить диалоговое окно, создайте класс, производный от `CFontDialog`, предоставить шаблон пользовательское диалоговое окно и добавить схему сообщений для обработки сообщений уведомления из расширенных элементов управления. Все необработанные сообщения должны передаваться в базовый класс.  
  
 Настройка функцию-обработчик не является обязательным.  
  
 Дополнительные сведения об использовании `CFontDialog`, в разделе [классы общих диалоговых окон](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdlgs.h  
  
##  <a name="cfontdialog"></a>CFontDialog::CFontDialog  
 Создает объект `CFontDialog`.  
  
```  
CFontDialog(
    LPLOGFONT lplfInitial = NULL,  
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,  
    DWORD dwFlags = CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);  
```  
  
### <a name="parameters"></a>Параметры  
 l`plfInitial`  
 Указатель на [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структура данных, которая позволяет настроить некоторые характеристики шрифта.  
  
 `charFormat`  
 Указатель на [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) структура данных, которая позволяет настроить некоторые характеристики шрифта в широкий элемент управления.  
  
 `dwFlags`  
 Указывает один или несколько флагов выбора шрифта. Одно или несколько предустановленных значений можно объединить с помощью побитового оператора OR. Если вы изменяете член структуры `m_cf.Flag`, используйте оператор OR в изменениях, чтобы сохранить поведение по умолчанию. Сведения о каждом из этих флагов см. в описании [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) в структуре [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 pdcPrinter  
 Указатель на контекст принтера. Если этот параметр задан, он указывает на контекст принтера, для которого выбираются шрифты.  
  
 `pParentWnd`  
 Указатель на родительское окно или окно владельца диалогового окна шрифта.  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что конструктор автоматически заполняет члены структуры `CHOOSEFONT`. Их следует изменять, только если вам требуется диалоговое окно, отличное от стандартного.  
  
> [!NOTE]
>  Первая версия этой функции существует, только если элементы управления форматированным редактированием не поддерживаются.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#78;](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CFontDialog::DoModal  
 Эта функция вызывается для отображения диалогового окна Windows распространенных шрифта и позволяет пользователю выбрать шрифт.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 **IDOK** или **IDCANCEL**. Если **IDCANCEL** будет возвращен, вызовите Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) функцию, чтобы определить, произошла ли ошибка.  
  
 **IDOK** и **IDCANCEL** константы, которые указывают, выбрал ли пользователь кнопку OK или "Отмена".  
  
### <a name="remarks"></a>Примечания  
 Если требуется инициализировать различные элементы управления диалогового окна шрифта, задав члены [m_cf](#m_cf) структуры, это следует сделать до вызова метода `DoModal`, но после создания объекта диалогового окна.  
  
 Если `DoModal` возвращает **IDOK**, можно вызвать другой член функции для получения параметров или данные, введенные пользователем в диалоговом окне.  
  
### <a name="example"></a>Пример  
  Примеры для [CFontDialog::CFontDialog](#cfontdialog) и [CFontDialog::GetColor](#getcolor).  
  
##  <a name="getcharformat"></a>CFontDialog::GetCharFormat  
 Извлекает форматирования символов в выбранный шрифт.  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `cf`  
 Объект [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) структуру, содержащую сведения о форматировании символов выбранного шрифта.  
  
##  <a name="getcolor"></a>CFontDialog::GetColor  
 Эта функция вызывается для получения цвет выбранного шрифта.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цвет выбранного шрифта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#79;](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="getcurrentfont"></a>CFontDialog::GetCurrentFont  
 Эта функция вызывается для назначить элементы характеристики выбранный шрифт [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) структуры.  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>Параметры  
 *lplf*  
 Указатель на `LOGFONT` структуры.  
  
### <a name="remarks"></a>Примечания  
 Другие `CFontDialog` функций-членов предоставляются для доступа к отдельным характеристик текущего шрифта.  
  
 Если эта функция вызывается во время вызова [DoModal](#domodal), он возвращает текущее выделение в то время (то, что пользователь видит или имеет изменены в диалоговом окне). Если эта функция вызывается после вызова `DoModal` (только если `DoModal` возвращает **IDOK**), он возвращает какие фактически выбранный пользователем.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#80;](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="getfacename"></a>CFontDialog::GetFaceName  
 Эта функция вызывается для получения имя шрифта выбранного шрифта.  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя начертания шрифта, выбранного в `CFontDialog` диалоговое окно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#81;](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="getsize"></a>CFontDialog::GetSize  
 Эта функция вызывается для получения размера выбранного шрифта.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер шрифта в десятых долях точки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#82;](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="getstylename"></a>CFontDialog::GetStyleName  
 Эта функция вызывается для получения имени стиля выбранного шрифта.  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя стиля шрифта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#83;](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="getweight"></a>CFontDialog::GetWeight  
 Эта функция вызывается для получения вес выбранного шрифта.  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вес выбранного шрифта.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о насыщенность шрифта см. в разделе [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#84;](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="isbold"></a>CFontDialog::IsBold  
 Вызывайте эту функцию, чтобы определить, является ли выбранный шрифт полужирным.  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выбранный шрифт полужирным характеристика включен; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#85;](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="isitalic"></a>CFontDialog::IsItalic  
 Вызывайте эту функцию, чтобы определить, является ли шрифт курсивом.  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выбранный шрифт характеризуется курсивом включен; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#86;](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="isstrikeout"></a>CFontDialog::IsStrikeOut  
 Эта функция вызывается для определения, если зачеркнутый отображается выбранный шрифт.  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выбранный шрифт характеризуется зачеркнутый включен; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#87;](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="isunderline"></a>CFontDialog::IsUnderline  
 Эта функция вызывается для определения, если выбранный шрифт подчеркнутым.  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выбранный шрифт характеризуется Подчеркивание включено; в противном случае — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#88;](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="m_cf"></a>CFontDialog::m_cf  
 Структуры, члены которого хранения характеристики объекта диалогового окна.  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>Примечания  
 После построения `CFontDialog` объекта, можно использовать `m_cf` для изменения различных аспектов диалоговым окном перед вызовом метода `DoModal` функции-члена. Дополнительные сведения о структуре см. в разделе [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#89;](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Пример MFC HIERSVR](../../visual-cpp-samples.md)   
 [Класс CCommonDialog](../../mfc/reference/ccommondialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




