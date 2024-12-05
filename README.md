```Swift
import Foundation

protocol SelfIntroductionDelegate: AnyObject {
    func didRequestSkills() -> [String]
    func didRequestProjects() -> [String]
    func didRequestAwards() -> [String]
}

final class Woongaaaa {
    weak var delegate: SelfIntroductionDelegate?
    
    func startIntroduction() {
        print("🛠 Skills: \(delegate?.didRequestSkills().joined(separator: ", ") ?? "None")")
        
        print("📚 Projects:")
        delegate?.didRequestProjects().forEach { print("- \($0)") }
        
        print("🏆 Awards:")
        delegate?.didRequestAwards().forEach { print("- \($0)") }
    }
}

class Profile: SelfIntroductionDelegate {
    func didRequestSkills() -> [String] {
        ["Swift", "UIKit"]
    }
    
    func didRequestProjects() -> [String] {
        [
            "메메(MEME): 나만의 메이크업 메이트",
            "스튜(STEW): 전국 대학교 제휴업체를 어디에서나!",
            "워크멍: 반려견 산책 매칭 앱 서비스"
        ]
    }
    
    func didRequestAwards() -> [String] {
        [
            "2023년도 창의공학설계 전시회 은상",
            "UMC 5th DEMODAY ExtraPrize"
        ]
    }
}

let woongaaaa = Woongaaaa()
let profile = Profile()
woongaaaa.delegate = profile
woongaaaa.startIntroduction()


