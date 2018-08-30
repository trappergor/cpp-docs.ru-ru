---
title: Класс CHotKeyCtrl | Документация Майкрософт
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
ms.openlocfilehash: 4a7f5cee986ad82790870bfa7684a99c60dc462e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43206270"
---
# <a name="chotkeyctrl-class"></a>Класс CHotKeyCtrl
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
|[CHotKeyCtrl::Create](#create)|Создает элемент управления "Горячий" ключа и присоединяет его к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::CreateEx](#createex)|Создает элемент управления "Горячий" ключа с указанным расширенные стили Windows и присоединяет его к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Извлекает виртуального ключа кода и флаги модификаторов для сочетания клавиш из "Горячий" ключа элемента управления.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Извлекает имя ключа в локальном кодировке, назначенные сочетания клавиш.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Извлекает имя ключа в локальном кодировке, назначенные указанного виртуального кода клавиши.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Задает "Горячий" сочетание клавиш для элемента управления "Горячий" ключа.|  
|[CHotKeyCtrl::SetRules](#setrules)|Определяет недопустимые сочетания и сочетания модификатор по умолчанию для горячей ключа элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 «Горячий ключа элемент управления» — окно, которое позволяет пользователю создавать сочетания клавиш. «Горячей» ключ — это сочетание клавиш, которое пользователь может нажать для быстрого выполнения действий. (К примеру, пользователь может создавать сочетания клавиш, который активирует данного окна и помещает его в верхнюю часть Z-порядка.) "Горячий" ключа выводит решения пользователя и гарантирует, что будет выбрано сочетание допустимых клавиш.  
  
 Этот элемент управления (и, следовательно `CHotKeyCtrl` класс) доступны только для программ, работающих в Windows 95/98 и Windows NT версии 3.51 и более поздних версиях.  
  
 Если пользователь выбрал сочетание клавиш, приложение можно извлекать заданное сочетание клавиш из элемента управления и настроить сочетания клавиш в системе с помощью WM_SETHOTKEY сообщения. Каждый раз, когда пользователь нажимает клавишу "Горячий" после этого из любой части системы, окна, указанную в сообщении WM_SETHOTKEY получает сообщение WM_SYSCOMMAND, указав SC_HOTKEY. Это сообщение активирует окно, которое получает его. Сочетания клавиш будет существовать до приложения, которое вызвало WM_SETHOTKEY завершает работу.  
  
 Этот механизм отличается от "Горячий" Поддержка ключа, зависящий от сообщения WM_HOTKEY и Windows [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309) и [UnregisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646327) функции.  
  
 Дополнительные сведения об использовании `CHotKeyCtrl`, см. в разделе [элементов управления](../../mfc/controls-mfc.md) и [использование CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
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
 Создает элемент управления "Горячий" ключа и присоединяет его к `CHotKeyCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 *dwStyle*  
 Задает стиль "Горячий" ключа элемента управления. Примените любое сочетание стилей элемента управления. См. в разделе [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в пакете SDK для Windows, Дополнительные сведения.  
  
 *Rect*  
 Задает размер и положение "Горячий" ключа элемента управления. Может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [структура RECT](../../mfc/reference/rect-structure1.md).  
  
 *pParentWnd*  
 Указывает горячих клавиш родительскому окну элемента управления, обычно [CDialog](../../mfc/reference/cdialog-class.md). Он не должен иметь значение NULL.  
  
 *nID*  
 Указывает идентификатор "Горячий" ключа элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае 0.  
  
### <a name="remarks"></a>Примечания  
 При создании `CHotKeyCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать `Create`, который создает горячей ключа элемента управления и прикрепляет его к `CHotKeyCtrl` объекта.  
  
 Если вы хотите использовать windows расширенных стилей с элементом управления, вызовите [CreateEx](#createex) вместо `Create`.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Вызывайте эту функцию для создания элемента управления (дочернего окна) и свяжите ее с `CHotKeyCtrl` объекта.  
  
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
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows, см. в разделе *dwExStyle* параметр для [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) в пакете Windows SDK.  
  
 *dwStyle*  
 Задает стиль "Горячий" ключа элемента управления. Примените любое сочетание стилей элемента управления. Дополнительные сведения см. в разделе [общие стили элемента управления](/windows/desktop/Controls/common-control-styles) в пакете Windows SDK.  
  
 *Rect*  
 Ссылку на [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) структура, описывающая размер и положение окна, создаваемых в клиентских координатах *pParentWnd*.  
  
 *pParentWnd*  
 Указатель на окно, которое является родительским для элемента управления.  
  
 *nID*  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) применение расширенных стилей Windows, определяемое префикс расширенного стиля Windows **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Извлекает виртуального ключа кода и флаги модификаторов для сочетания клавиш из "Горячий" ключа элемента управления.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [out] *wVirtualKeyCode*  
 Виртуальному коду клавиши сочетания клавиш. Список стандартных коды виртуальных клавиш см. в разделе Winuser.h.  
  
 [out] *wModifiers*  
 Побитовое сочетание (OR) флагов, которое указывает клавиши-модификаторы в сочетании клавиш.  
  
 Далее приведены флаги модификаторов.  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT - клавиша|  
|HOTKEYF_CONTROL|Клавиша CTRL|  
|HOTKEYF_EXT|Расширенный ключ|  
|HOTKEYF_SHIFT|Клавиша SHIFT|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом перегруженный метод, значение DWORD, содержащее виртуальный ключа кода и флаги модификаторов. Младший байт слова низкого порядка содержит виртуального кода клавиши, старший байт слова низкого порядка содержит флаги модификаторов и старшее слово равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Виртуального кода клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Вызывайте эту функцию члена, чтобы получить локализованное название сочетания клавиш.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя текущего выбранного сочетания клавиш. Если отсутствует выбранный ключ "Горячий", `GetHotKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя, которое возвращает эта функция-член поступают из драйвер клавиатуры. Вы можете установить драйвер нелокализованное клавиатуры в локализованной версии Windows и наоборот.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Вызывайте эту функцию член, чтобы получить локализованное имя ключа, назначенный для указанного виртуального кода клавиши.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Параметры  
 *Vk*  
 Виртуального кода клавиши.  
  
 *fExtended*  
 Если виртуального кода клавиши представляет собой расширенный ключ, значение TRUE; в противном случае — значение FALSE.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя ключа, заданного параметром *vk* параметра. Если ключ не имеет сопоставленного имени, `GetKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя ключа, которую возвращает эта функция поставляется в драйвере клавиатуры, чтобы установить драйвер нелокализованное клавиатуры в локализованной версии Windows и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Задает сочетание клавиш для элемента управления "Горячий" ключа.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *wVirtualKeyCode*  
 Виртуальному коду клавиши сочетания клавиш. Список стандартных коды виртуальных клавиш см. в разделе Winuser.h.  
  
 [in] *wModifiers*  
 Побитовое сочетание (OR) флагов, которое указывает клавиши-модификаторы в сочетании клавиш.  
  
 Далее приведены флаги модификаторов.  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT - клавиша|  
|HOTKEYF_CONTROL|Клавиша CTRL|  
|HOTKEYF_EXT|Расширенный ключ|  
|HOTKEYF_SHIFT|Клавиша SHIFT|  
  
### <a name="remarks"></a>Примечания  
 Виртуального кода клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Вызывайте эту функцию, чтобы определить недопустимые сочетания и сочетания модификатор по умолчанию для элемента управления "Горячий" ключа.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 *wInvalidComb*  
 Массив флагов, указывающее недопустимые сочетания клавиш. Это может быть сочетанием следующих значений:  
  
- HKCOMB_A ALT  
  
- HKCOMB_C CTRL  
  
- HKCOMB_CA CTRL + ALT  
  
- Неизмененный HKCOMB_NONE ключи  
  
- HKCOMB_S SHIFT  
  
- HKCOMB_SA SHIFT + ALT  
  
- HKCOMB_SC SHIFT + CTRL  
  
- HKCOMB_SCA SHIFT + CTRL + ALT  
  
 *wModifiers*  
 Массив флагов, указывающее сочетание клавиш для использования, когда пользователь вводит недопустимое сочетание. Дополнительные сведения о флаги модификаторов, см. в разделе [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Примечания  
 Если пользователь вводит недопустимое сочетание клавиш, как определено флагов, указанных в *wInvalidComb*, система использует оператор OR для объединения ключей, введенный пользователем с помощью флагов, указанных в *wModifiers*. Итоговый сочетание клавиш преобразуется в строку и затем отображаются в элементе управления "Горячий" ключа.  
  
## <a name="see-also"></a>См. также  
 [Класс CWnd](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



