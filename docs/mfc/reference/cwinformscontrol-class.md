---
title: "Класс CWinFormsControl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsControl class
- Windows Forms [C++], MFC support
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
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
ms.openlocfilehash: 49e24c04deda3df5683908fa9ca485cf7802214b
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformscontrol-class"></a>Класс CWinFormsControl
Предоставляет базовую функцию для размещения элементов управления Windows Forms.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Параметры  
 `TManagedControl`  
 Элемент управления .NET Framework Windows Forms для отображения в приложении MFC.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Создает объект оболочки элемента управления MFC Windows Forms.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Создает элемент управления Windows Forms в контейнере MFC.|  
|[CWinFormsControl::GetControl](#getcontrol)|Извлекает указатель на элемент управления Windows Forms.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Получает дескриптор для элемента управления Windows Forms.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Приведение типа как указатель на элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 `CWinFormsControl` Класс предоставляет основные функциональные возможности для размещения элементов управления Windows Forms.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Код MFC не следует кэшировать дескриптора окна (обычно хранится в `m_hWnd`). Некоторые свойства элемента управления Windows Forms, требуют базовой Win32 `Window` быть уничтожается и создается заново с помощью `DestroyWindow` и `CreateWindow`. Реализация обрабатывает MFC Windows Forms `Destroy` и `Create` событий элементов управления для обновления `m_hWnd` член.  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (в котором определена AFXDLL).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 Создает элемент управления Windows Forms в контейнере MFC.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Параметры  
 `pType`  
 Тип данных создаваемого элемента управления. Должно быть [тип](https://msdn.microsoft.com/en-us/library/system.type) тип данных.  
  
 `dwStyle`  
 Стиль окна, чтобы применить к элементу управления. Определение сочетания [стили окна](../../mfc/reference/window-styles.md). В настоящее время поддерживаются только следующие стили: WS_TABSTOP, WS_VISIBLE, WS_DISABLED и WS_GROUP.  
  
 `rect`  
 Объект [структура RECT](../../mfc/reference/rect-structure1.md) , определяющий координаты верхний левый и правый нижний углы элемента управления (первая перегрузка только).  
  
 `nPlaceHolderID`  
 Дескриптор элемента управления владельца статических месте помещаются в редакторе ресурсов. Статический элемент управления, при условии, что его позицию z порядка и стили заменяет вновь созданного элемента управления Windows Forms (второй перегрузка только).  
  
 `pParentWnd`  
 Указатель на родительское окно.  
  
 `nID`  
 Идентификатор ресурса должен назначаться вновь созданного элемента управления.  
  
 `pControl`  
 Экземпляр элемента управления Windows Forms должно быть связано с [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) объекта (только для четвертого перегрузку).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ненулевое значение. Если операция завершилась неудачей, возвращает нуль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает экземпляр элемента управления .NET Framework Windows Forms в контейнере MFC.  
  
 Первый перегруженный метод принимает тип данных .NET Framework `pType` таким образом, чтобы MFC можно создать экземпляр объекта этого типа. `pType`должно быть [тип](https://msdn.microsoft.com/en-us/library/system.type) тип данных.  
  
 Вторая перегрузка метода создает элемент управления Windows Forms на основе `TManagedControl` параметр шаблона `CWinFormsControl` класса. Размер и положение элемента управления основан на `RECT` структуры передается в метод. Только `dwStyle` важно для стилей.  
  
 Третья перегрузка метода создает элемент управления Windows Forms, который заменяет статический элемент управления, его удаления и при условии, что его позицию z порядка и стили. Статический элемент управления используется только как заполнитель для элемента управления Windows Forms. При создании элемента управления, эта перегрузка объединяет стили из `dwStyle` со стилями ресурсов статического элемента управления.  
  
 Четвертый перегрузка метода позволяет передавать в уже созданный экземпляр элемента управления Windows Forms `pControl` , выбранную в MFC. Он должен быть того же типа, что `TManagedControl` параметр шаблона `CWinFormsControl` класса.  
  
 В разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) примеры на форме Windows Forms с помощью элементов управления.  
  
##  <a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 Создает объект оболочки элемента управления MFC Windows Forms.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления Windows Forms создается при вызове [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrol"></a>CWinFormsControl::GetControl  
 Извлекает указатель на элемент управления Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на элемент управления Windows Forms.  
  
### <a name="example"></a>Пример  
  В разделе [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Получает дескриптор для элемента управления Windows Forms.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для элемента управления Windows Forms.  
  
### <a name="remarks"></a>Примечания  
 `GetControlHandle`— Это вспомогательный метод, который возвращает дескриптор окна, хранятся в свойствах элемента управления .NET Framework. Значение дескриптора окна копируется в [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) при вызове [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.  
  
 Дополнительные сведения о Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Приведение типа как указатель на элемент управления Windows Forms.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор передает `CWinFormsControl<``TManagedControl``>` функций, которые принимают указатель на элемент управления Windows Forms.  
  
## <a name="see-also"></a>См. также  
 [Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)   
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)

