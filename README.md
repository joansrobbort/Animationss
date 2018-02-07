if sender.isOn == true {
            shouldRepeatBool = true
            UIView.animate(withDuration: 0.25, animations: {
               // self.ViewRepeating.needsUpdateConstraints()
                self.HieghtContrent.constant = 70
                self.RepeatingHeightConstrant.constant = 68 + 70
                self.view.layoutIfNeeded()
            })
        }
        else
        {
            shouldRepeatBool = false
            UIView.animate(withDuration: 0.25, animations: {
               // self.ViewRepeating.needsUpdateConstraints()
                self.HieghtContrent.constant = 0
                self.RepeatingHeightConstrant.constant = 68
                self.view.layoutIfNeeded()
            })
        }
    }
    
================================================


import UIKit

class ExSlideMenuController : SlideMenuController {

    override func isTagetViewController() -> Bool {
        if let vc = UIApplication.topViewController() {
            if vc is ClientDetaileVC {
                return true
            }
//            if vc is ProfileVC {
//                return true
//            }
//            if vc is SettingsVC {
//                return true
//            }
//            if vc is ProductsVC {
//                return true
//            }
        }
        return false
    }
    
    override func track(_ trackAction: TrackAction) {
        switch trackAction {
        case .leftTapOpen:
            print("TrackAction: left tap open.")
        case .leftTapClose:
            print("TrackAction: left tap close.")
        case .leftFlickOpen:
            print("TrackAction: left flick open.")
        case .leftFlickClose:
            print("TrackAction: left flick close.")
        default :
            break
        }   
    }
}
