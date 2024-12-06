```Swift
import Foundation

struct MyProfile {
    let name: String
    let skills: [String]
    let projects: [String]
    let awards: [String]
    
    func introduce() {
        print("👋 안녕하세요! \(name)입니다.")
        print("\n🛠 Skills: \(skills.joined(separator: ", "))")
        print("\n📚 Projects:")
        projects.forEach { print("- \($0)") }
        print("\n🏆 Awards:")
        awards.forEach { print("- \($0)") }
    }
}

let myProfile = MyProfile(
    name: "황채웅",
    skills: ["Swift", "UIKit"],
    projects: [
        "메메(MEME): 나만의 메이크업 메이트",
        "스튜(STEW): 전국 대학교 제휴업체를 어디에서나!",
        "워크멍: 반려견 산책 매칭 앱 서비스"
    ],
    awards: [
        "2023년도 창의공학설계 전시회 은상",
        "UMC 5th DEMODAY ExtraPrize"
    ]
)

myProfile.introduce()
