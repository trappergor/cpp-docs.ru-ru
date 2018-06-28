---
title: CHotKeyCtrl-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365f984385eab870d46b0772719346fa5d1ae383
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040159"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "горячая клавиша" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Создает объект `CHotKeyCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Создает горячей ключа управления и прикрепляет его к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::CreateEx](#createex)|Создает элемент управления горячей ключа с указанным расширенные стили Windows и прикрепляет его к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Получает виртуальный ключа код и модификатор флаги сочетания клавиш из горячей ключа элемента управления.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Возвращает имя ключа в наборе локальных символов, назначенные сочетания клавиш.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Возвращает имя ключа локального кодировка, назначенный для указанного виртуального кода клавиши.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Задает горячей сочетание клавиш для сочетания ключа элемента управления.|  
|[CHotKeyCtrl::SetRules](#setrules)|Определяет недопустимые сочетания и комбинации модификатор по умолчанию для горячего ключа элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 «Горячей ключа управления» — это окно, позволяющее создавать сочетания клавиш. «Сочетания клавиш» является сочетание клавиш, которое пользователь может нажать для быстрого выполнения действий. (Например, пользователь может создавать сочетания клавиш, которое активирует данного окна и переводит ее в верхней части Z-порядка). Горячий ключа элемент управления отображает выбор пользователя и гарантирует, что пользователь выбирает допустимое сочетание клавиш.  
  
 Этот элемент управления (и, следовательно, `CHotKeyCtrl` класс) доступен только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних.  
  
 Если пользователь выбрал сочетание клавиш, приложение можно получить заданное сочетание клавиш из элемента управления и использовать **WM_SETHOTKEY** сообщение, чтобы настроить сочетания клавиш в системе. Всякий раз, когда пользователь нажимает сочетание клавиш таким образом, из любой части системы, окна, указываемой **WM_SETHOTKEY** получает сообщение **WM_SYSCOMMAND** указание сообщение **SC_HOTKEY** . Это сообщение активирует окно, получает его. Сочетания клавиш остается действительным, пока приложение, вызвавшее **WM_SETHOTKEY** завершает работу.  
  
 Этот механизм отличается от возможностей горячей ключа, зависит от **WM_HOTKEY** сообщение и Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) и [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) функции.  
  
 Дополнительные сведения об использовании `CHotKeyCtrl`, в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 Создает объект `CHotKeyCtrl`.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 Создает горячей ключа управления и прикрепляет его к `CHotKeyCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Задает стиль горячей ключа элемента управления. Примените любое сочетание стилей элемента управления. В разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в Windows SDK для получения дополнительной информации.  
  
 *Rect*  
 Задает размер и положение горячей ключа элемента управления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [структура RECT](../../mfc/reference/rect-structure1.md).  
  
 *pParentWnd*  
 Указывает горячей ключа родительского окна элемента управления, обычно [CDialog](../../mfc/reference/cdialog-class.md). Он не должен быть **NULL**.  
  
 *nID*  
 Указывает идентификатор горячей ключа элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CHotKeyCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает горячей ключа элемента управления и прикрепляет его к `CHotKeyCtrl` объекта.  
  
 Если вы хотите использовать с элементом управления windows расширенных стилей, вызовите [CreateEx](#createex) вместо `Create`.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Эта функция вызывается для создания элемента управления (дочернего окна) и связать его с `CHotKeyCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwExStyle*  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе *dwExStyle* параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в Windows SDK.  
  
 *dwStyle*  
 Задает стиль горячей ключа элемента управления. Примените любое сочетание стилей элемента управления. Дополнительные сведения см. в разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в Windows SDK.  
  
 *Rect*  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна будет создан в клиентские координаты *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, который является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенные стили Windows, заданные вводной части расширенный стиль Windows **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Получает виртуальный ключа код и модификатор флаги сочетания клавиш из горячей ключа элемента управления.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *wVirtualKeyCode*  
 Виртуальному коду клавиши сочетания клавиш. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
 [out] *wModifiers*  
 Побитовое сочетание (OR) флагов, которое указывает клавиши-модификаторы клавиш.  
  
 Существуют следующие флаги модификаторов.  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT - клавиша|  
|`HOTKEYF_CONTROL`|Нажмите клавишу CTRL|  
|`HOTKEYF_EXT`|Расширенные ключ|  
|`HOTKEYF_SHIFT`|Клавиша SHIFT|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом перегруженный метод, `DWORD` , содержащий виртуальный ключа код и модификатор флаги. Младший байт слова низкого порядка содержит виртуального кода клавиши, старший байт слова низкого порядка содержит флаги модификаторов и старшее слово равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Виртуального кода клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Вызовите эту функцию-член получить локализованное название сочетания клавиш.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя выбранного сочетания клавиш. Если нет выбранных горячей ключа `GetHotKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя, которое возвращает эта функция-член поступает из драйвер клавиатуры. Можно установить драйвер нелокализованное клавиатуры в локализованной версии Windows и наоборот.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Вызовите эту функцию-член для получения локализованного имени ключа, назначенный для указанного виртуального кода клавиши.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Параметры  
 *Vk*  
 Виртуальному коду клавиши.  
  
 *fExtended*  
 Если ключ расширенного виртуального кода клавиши **TRUE**; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя ключа, указанного *vk* параметра. Если ключ не имеет сопоставленного имени, `GetKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя ключа, эта функция возвращает поступают из драйвер клавиатуры, поэтому можно установить драйвер нелокализованное клавиатуры в локализованной версии Windows и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Задает сочетание клавиш для сочетания ключа элемента управления.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *wVirtualKeyCode*  
 Виртуальному коду клавиши сочетания клавиш. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
 [in] *wModifiers*  
 Побитовое сочетание (OR) флагов, которое указывает клавиши-модификаторы клавиш.  
  
 Существуют следующие флаги модификаторов.  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT - клавиша|  
|`HOTKEYF_CONTROL`|Нажмите клавишу CTRL|  
|`HOTKEYF_EXT`|Расширенные ключ|  
|`HOTKEYF_SHIFT`|Клавиша SHIFT|  
  
### <a name="remarks"></a>Примечания  
 Виртуального кода клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Эта функция вызывается для определения недопустимые сочетания и комбинации модификатор по умолчанию для горячего ключа элемента управления.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 *wInvalidComb*  
 Массив флагов, задающий недопустимые сочетания клавиш. Он может быть сочетанием следующих значений:  
  
- `HKCOMB_A` ALT  
  
- `HKCOMB_C` CTRL  
  
- `HKCOMB_CA` CTRL + ALT  
  
- `HKCOMB_NONE` Без изменений ключей  
  
- `HKCOMB_S` SHIFT  
  
- `HKCOMB_SA` SHIFT + ALT  
  
- `HKCOMB_SC` SHIFT + CTRL  
  
- `HKCOMB_SCA` SHIFT + CTRL + ALT  
  
 *wModifiers*  
 Массив флагов, задающий сочетание клавиш для использования, когда пользователь вводит недопустимую комбинацию. Дополнительные сведения о флагах модификатор см. в разделе [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Примечания  
 Если пользователь вводит недопустимое сочетание клавиш, в соответствии с определением флагов, заданных в *wInvalidComb*, система использует оператор OR для объединения ключей, введенные пользователем с помощью флагов, заданных в *wModifiers*. Полученный сочетание клавиш преобразуется в строку и затем отображаются в активном ключа управления.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



