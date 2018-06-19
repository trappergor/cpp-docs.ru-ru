---
title: Класс CMFCAcceleratorKey | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
dev_langs:
- C++
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6ca49fd2696a8fc5a488962f1f13ead1d861c20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369535"
---
# <a name="cmfcacceleratorkey-class"></a>Класс CMFCAcceleratorKey
Вспомогательный класс, реализующий виртуальное ключевое сопоставление и форматирование.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCAcceleratorKey : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKey::CMFCAcceleratorKey](#cmfcacceleratorkey)|Создает объект `CMFCAcceleratorKey`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCAcceleratorKey::Format](#format)|Преобразует структуры, УСКОРЕНИЕ визуальное представление.|  
|[CMFCAcceleratorKey::SetAccelerator](#setaccelerator)|Задает сочетание клавиш для `CMFCAcceleratorKey` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Сочетания клавиш также называются сочетания клавиш. Если вы хотите отобразить сочетания клавиш, которые пользователь вводит, [класс CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) maps сочетания клавиш, например Alt + Shift + S, пользовательский текстовый формат, например «Alt + Shift + S». Каждый `CMFCAcceleratorKey` объект сопоставляется одному сочетанию клавиш в текстовом формате.  
  
 Дополнительные сведения об использовании сочетаний клавиш и таблицы сочетаний клавиш см. в разделе [CKeyboardManager класса](../../mfc/reference/ckeyboardmanager-class.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует `CMFCAcceleratorKey` объекта и как использовать его `Format` метод.  
  
 [!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAcceleratorKey`   
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxacceleratorkey.h  
  
##  <a name="cmfcacceleratorkey"></a>  CMFCAcceleratorKey::CMFCAcceleratorKey  
 Создает [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта.  
  
```  
CMFCAcceleratorKey();  
CMFCAcceleratorKey(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpAccel`  
 Указатель на сочетание клавиш.  
  
### <a name="remarks"></a>Примечания  
 Если при создании не указано сочетание клавиш `CMFCAccleratorKey`, используйте [CMFCAcceleratorKey::SetAccelerator](#setaccelerator) способ сопоставления сочетания клавиш с вашей `CMFCAcceleratorKey` объекта.  
  
##  <a name="format"></a>  CMFCAcceleratorKey::Format  
 Преобразует структуру УСКОРЕНИЕ связанного строковому значению.  
  
```  
void Format(CString& str) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `str`  
 Ссылку на `CString` объекта, где метод записывает переведенные сочетания клавиш.  
  
### <a name="remarks"></a>Примечания  
 Этот метод извлекает строковое формат сочетанием клавиш. Можно задать формат строки для [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта с помощью конструктора или метода [CMFCAcceleratorKey::SetAccelerator](#setaccelerator).  
  
##  <a name="setaccelerator"></a>  CMFCAcceleratorKey::SetAccelerator  
 Задает сочетание клавиш для [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) объекта.  
  
```  
void SetAccelerator(LPACCEL lpAccel);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpAccel`  
 Указатель на сочетание клавиш.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы задать сочетание клавиш для `CMFCAcceleratorKey` Если вы не указали сочетания клавиш при создании `CMFCAcceleratorKey`.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
