# digital-clock-in-swift
it was a  digital clock in swiftui
content view 


#####
###
import SwiftUI

@main
struct WATERREMAINDERApp: App {
    var body: some Scene {
        WindowGroup {
            ClockApp()
        }
    }
}



mainview
####

import SwiftUI

struct ClockApp: View {
    @State private var currentDate = Date()

    var body: some View {
        VStack {
            Text("Focus Clock")
                .font(.title)
                .padding()

            Spacer()

            Text(getFormattedTime())
                .font(.system(size: 100, weight: .bold, design: .rounded))
                .padding()

            Text("Focus on your work you want to do!")
                .font(.headline)
                .foregroundColor(.blue)
                .padding()

            Spacer()
        }
        .padding()
        .onAppear {
            // Update the time every second
            Timer.scheduledTimer(withTimeInterval: 1, repeats: true) { _ in
                currentDate = Date()
            }
        }
    }

    func getFormattedTime() -> String {
        let formatter = DateFormatter()
        formatter.dateFormat = "HH:mm:ss"
        return formatter.string(from: currentDate)
    }
}

struct ClockApp_Previews: PreviewProvider {
    static var previews: some View {
        ClockApp()
    }
}


