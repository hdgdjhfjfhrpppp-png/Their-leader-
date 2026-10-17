local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local StarterGui = game:GetService("StarterGui")
local localPlayer = Players.LocalPlayer
local PlayerGui = localPlayer:WaitForChild("PlayerGui")

pcall(function()
    StarterGui:SetCore("SendNotification", {
        Title = "نيتروس وكبيرهم",
        Text = "السكربت قيد التحميل يرجى الانتظار...",
        Duration = 5
    })
end)

if PlayerGui:FindFirstChild("VR7_MercyUI") then
    PlayerGui.VR7_MercyUI:Destroy()
end

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "VR7_MercyUI"
ScreenGui.Parent = PlayerGui
ScreenGui.ResetOnSpawn = false

local IntroLabel = Instance.new("TextLabel")
IntroLabel.Name = "IntroLabel"
IntroLabel.Parent = ScreenGui
IntroLabel.BackgroundTransparency = 1
IntroLabel.Position = UDim2.new(0.5, -250, 0.5, -50)
IntroLabel.Size = UDim2.new(0, 500, 0, 100)
IntroLabel.Font = Enum.Font.SourceSansBold
IntroLabel.Text = "كبيرهم وسكارل"
IntroLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
IntroLabel.TextSize = 36
IntroLabel.TextXAlignment = Enum.TextXAlignment.Center

task.spawn(function()
    local colors = {
        Color3.fromRGB(255, 0, 0),
        Color3.fromRGB(0, 255, 0),
        Color3.fromRGB(0, 150, 255),
        Color3.fromRGB(255, 255, 0),
        Color3.fromRGB(255, 0, 255)
    }
    local index = 1
    local startTime = tick()
    while tick() - startTime < 5 do
        IntroLabel.TextColor3 = colors[index]
        index = (index % #colors) + 1
        task.wait(0.3)
    end
    if IntroLabel and IntroLabel.Parent then
        IntroLabel:Destroy()
    end
end)

local MainFrame = Instance.new("Frame")
MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
MainFrame.BorderColor3 = Color3.fromRGB(180, 0, 0)
MainFrame.BorderSizePixel = 2
MainFrame.Position = UDim2.new(0.5, -275, 0.5, -175)
MainFrame.Size = UDim2.new(0, 550, 0, 350)
MainFrame.Visible = false
MainFrame.Active = true
MainFrame.Draggable = true

local TitleBar = Instance.new("TextLabel")
TitleBar.Name = "TitleBar"
TitleBar.Parent = MainFrame
TitleBar.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
TitleBar.BorderColor3 = Color3.fromRGB(180, 0, 0)
TitleBar.Size = UDim2.new(1, 0, 0, 35)
TitleBar.Font = Enum.Font.SourceSansBold
TitleBar.Text = "  صمله"
TitleBar.TextColor3 = Color3.fromRGB(220, 220, 220)
TitleBar.TextSize = 16
TitleBar.TextXAlignment = Enum.TextXAlignment.Left

local Sidebar = Instance.new("ScrollingFrame")
Sidebar.Name = "Sidebar"
Sidebar.Parent = MainFrame
Sidebar.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Sidebar.BorderColor3 = Color3.fromRGB(180, 0, 0)
Sidebar.Position = UDim2.new(0, 0, 0, 35)
Sidebar.Size = UDim2.new(0, 140, 1, -35)
Sidebar.CanvasSize = UDim2.new(0, 0, 2.4, 0)
Sidebar.ScrollBarThickness = 4
Sidebar.ZIndex = 5

local UIListLayout = Instance.new("UIListLayout")
UIListLayout.Parent = Sidebar
UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout.Padding = UDim.new(0, 4)

local ContentArea = Instance.new("Frame")
ContentArea.Name = "ContentArea"
ContentArea.Parent = MainFrame
ContentArea.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
ContentArea.BorderColor3 = Color3.fromRGB(180, 0, 0)
ContentArea.Position = UDim2.new(0, 145, 0, 40)
ContentArea.Size = UDim2.new(1, -150, 1, -45)

local PagesFolder = Instance.new("Folder")
PagesFolder.Name = "PagesFolder"
PagesFolder.Parent = ContentArea

local allPages = {}

local function createTabAndPage(name, order, canvasHeight)
    local btn = Instance.new("TextButton")
    btn.Name = name .. "Tab"
    btn.Parent = Sidebar
    btn.BackgroundColor3 = Color3.fromRGB(150, 0, 0)
    btn.BorderColor3 = Color3.fromRGB(200, 0, 0)
    btn.Size = UDim2.new(1, -10, 0, 32)
    btn.LayoutOrder = order
    btn.ZIndex = 6
    btn.Font = Enum.Font.SourceSansBold
    btn.Text = name
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 14

    local page = Instance.new("ScrollingFrame")
    page.Name = name .. "Page"
    page.Parent = PagesFolder
    page.BackgroundTransparency = 1
    page.Size = UDim2.new(1, 0, 1, 0)
    page.CanvasSize = UDim2.new(0, 0, canvasHeight or 4, 0)
    page.Visible = (order == 1)
    page.ScrollBarThickness = 4

    table.insert(allPages, page)

    btn.MouseButton1Click:Connect(function()
        for _, p in ipairs(allPages) do
            p.Visible = false
        end
        page.Visible = true
    end)

    return page
end

local HomeP = createTabAndPage("الرئيسية | Home", 1, 1.5)
local ScriptsP = createTabAndPage("سكربتات", 2, 16.5)
local CommandsP = createTabAndPage("أوامر", 3, 14.5)
local TargetP = createTabAndPage("استهداف | Target", 4, 2.5)
local TrackerP = createTabAndPage("تتبع اللاعب", 5, 4)
local MiscP = createTabAndPage("نصايح كبيرهم ونيتروس", 6, 4.5)

local ProfileBox = Instance.new("Frame")
ProfileBox.Name = "ProfileBox"
ProfileBox.Parent = HomeP
ProfileBox.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
ProfileBox.BorderColor3 = Color3.fromRGB(180, 0, 0)
ProfileBox.Position = UDim2.new(0, 10, 0, 10)
ProfileBox.Size = UDim2.new(0, 120, 0, 120)

local AvatarImage = Instance.new("ImageLabel")
AvatarImage.Name = "AvatarImage"
AvatarImage.Parent = ProfileBox
AvatarImage.BackgroundTransparency = 1
AvatarImage.Size = UDim2.new(1, 0, 1, 0)
AvatarImage.Image = Players:GetUserThumbnailAsync(localPlayer.UserId, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size420x420)

local InfoLabel = Instance.new("TextLabel")
InfoLabel.Name = "InfoLabel"
InfoLabel.Parent = HomeP
InfoLabel.BackgroundTransparency = 1
InfoLabel.Position = UDim2.new(0, 140, 0, 10)
InfoLabel.Size = UDim2.new(1, -150, 0, 120)
InfoLabel.Font = Enum.Font.SourceSansBold
InfoLabel.Text = "مطورين السكربت:\nالمطور الكبير كبيرهم 🇮🇶 : m_44407\nالمطور سكارل 🇮🇶 : 5n..8"
InfoLabel.TextColor3 = Color3.fromRGB(240, 240, 240)
InfoLabel.TextSize = 13
InfoLabel.TextXAlignment = Enum.TextXAlignment.Left
InfoLabel.TextYAlignment = Enum.TextYAlignment.Top

local NoticeBox = Instance.new("Frame")
NoticeBox.Name = "NoticeBox"
NoticeBox.Parent = HomeP
NoticeBox.BackgroundColor3 = Color3.fromRGB(25, 10, 10)
NoticeBox.BorderColor3 = Color3.fromRGB(180, 0, 0)
NoticeBox.Position = UDim2.new(0, 10, 0, 145)
NoticeBox.Size = UDim2.new(1, -20, 0, 100)

local NoticeText = Instance.new("TextLabel")
NoticeText.Name = "NoticeText"
NoticeText.Parent = NoticeBox
NoticeText.BackgroundTransparency = 1
NoticeText.Size = UDim2.new(1, 0, 1, 0)
NoticeText.Font = Enum.Font.SourceSansBold
NoticeText.Text = "جميع الحقوق محفوظة للمطورين كبيرهم و سكارل 🇮🇶\nالمطورين غير مسؤولين عن سوء الاستخدام.\n\nتتمنى ان يعجبك السكريبت."
NoticeText.TextColor3 = Color3.fromRGB(255, 120, 120)
NoticeText.TextSize = 13
NoticeText.TextWrapped = true

local TipsTitle = Instance.new("TextLabel")
TipsTitle.Name = "TipsTitle"
TipsTitle.Parent = MiscP
TipsTitle.BackgroundTransparency = 1
TipsTitle.Position = UDim2.new(0, 10, 0, 10)
TipsTitle.Size = UDim2.new(1, -20, 0, 30)
TipsTitle.Font = Enum.Font.SourceSansBold
TipsTitle.Text = "نصايح كبيرهم ونيتروس"
TipsTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
TipsTitle.TextSize = 15
TipsTitle.TextXAlignment = Enum.TextXAlignment.Left

local tipsContent = Instance.new("TextLabel")
tipsContent.Name = "TipsContent"
tipsContent.Parent = MiscP
tipsContent.BackgroundColor3 = Color3.fromRGB(25, 10, 10)
tipsContent.BorderColor3 = Color3.fromRGB(180, 0, 0)
tipsContent.Position = UDim2.new(0, 10, 0, 45)
tipsContent.Size = UDim2.new(1, -20, 0, 340)
tipsContent.Font = Enum.Font.SourceSansBold
tipsContent.Text = [[1. موبايلك خليه ع الشحن دائماً.
2. اكعد قريب ع الراوتر حتى البنج يبقى ثابت.
3. دير بالك تخلي الموبايل جوه المخده.
4. لا تخلي الموبايل ع الفراش.
5. خلي الموبايل ع الكاشي أو المرمر جوه السبوت أو السبلت.
6. استخدم كيبل شحن أبو الـ 3 رؤوس.
7. شد لك UPS حتى لو طفت الكهرباء.
8. طفي التطبيقات المفتوحة بالخلفية وافتح سكربتات منع الاق.
9. نزل جرافيك اللعبة للـ 1.
10. ريحه دقيقتين إذا حسيت الموبايل سخن حيل.]]
tipsContent.TextColor3 = Color3.fromRGB(240, 200, 200)
tipsContent.TextSize = 13
tipsContent.TextWrapped = true
tipsContent.TextXAlignment = Enum.TextXAlignment.Left
tipsContent.TextYAlignment = Enum.TextYAlignment.Top

local scriptButtons = {
    {"تشغيل سكربت: صمود (Anti-AFK)", "https://rawscripts.net/raw/Universal-Script-AntiAFK-v-AntiKick-V3-v-Kick-Attempt-Logger-27977"},
    {"تشغيل سكربت: طيران (Fly)", "https://rawscripts.net/raw/Universal-Script-Fly-V3-55253"},
    {"كبيرهم مال 7AMS", "https://raw.githubusercontent.com/hdgdjhfjfhrpppp-png/N9_7AMS-/refs/heads/main/N9_7AMS"},
    {"كبيرهم الوحش", "https://raw.githubusercontent.com/hdgdjhfjfhrpppp-png/infoj/refs/heads/main/README.md"},
    {"صمود 2", "https://rawscripts.net/raw/Universal-Script-Anti-afk-lol-28917"},
    {"تحسين الفريمات", "https://pastefy.app/OruW5AwY/raw"},
    {"فارس ممانع الاق", "https://rawusercontent.com/ook314745-svg/ANTILAGGER/refs/heads/main/obfuscated.lua%20(4).txt"},
    {"صمود 3", "https://rawscripts.net/raw/Universal-Script-AntiAFK-script-18076"},
    {"سكربت حموده", "https://raw.githubusercontent.com/SALAH142876/HAMODAH_ON_TOP/refs/heads/main/Protected_7545697692462583.txt"},
    {"سكربت لاست", "https://raw.githubusercontent.com/hdgdjhfjfhrpppp-png/N9_7AMS/refs/heads/main/README.md"},
    {"سكربت الاخضر afk", "https://rawscripts.net/raw/Universal-Script-Anti-afk-lol-28917"}
}

for i, data in ipairs(scriptButtons) do
    local btn = Instance.new("TextButton")
    btn.Name = "ScriptBtn_" .. i
    btn.Parent = ScriptsP
    btn.BackgroundColor3 = Color3.fromRGB(150, 0, 0)
    btn.BorderColor3 = Color3.fromRGB(200, 0, 0)
    btn.Position = UDim2.new(0, 10, 0, 50 + (i - 1) * 50)
    btn.Size = UDim2.new(1, -20, 0, 40)
    btn.Font = Enum.Font.SourceSansBold
    btn.Text = data[1]
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 14

    local url = data[2]
    btn.MouseButton1Click:Connect(function()
        pcall(function()
            loadstring(game:HttpGet(url))()
        end)
        btn.Text = "تم تشغيل: " .. data[1]
        btn.BackgroundColor3 = Color3.fromRGB(30, 130, 30)
    end)
end

local commandsList = {
    "clearerror", "chams", "datalimit 0.1", "Autokeypress", "Autokeypress nan", "Autokeypress inf",
    "Autokeypress 9", "Autokeypress w", "Autokeypress h", "antikick on", "antiafk on", "antiidle on",
    "freezeua", "fulbright", "fr", "nogshadown", "nogshadown 400", "nofog", "nogui", "nofog 0.1",
    "nofog nan", "nofog inf", "brightness nan", "brightness inf", "noclip", "noted", "Replicationlag 0.1",
    "backtrack 0.1", "setfpscap 24", "autokeypress hdonwndelay", "destroyheight", "clearnilinstances",
    "removeterrain", "cleargamewaypoints", "clearwaypoints", "breakloops", "norender", "use2022materials",
    "antigameplaypaused", "fov 1000"
}

for i, cmdText in ipairs(commandsList) do
    local btn = Instance.new("TextButton")
    btn.Name = "CmdBtn_" .. i
    btn.Parent = CommandsP
    btn.BackgroundColor3 = Color3.fromRGB(120, 20, 20)
    btn.BorderColor3 = Color3.fromRGB(180, 0, 0)
    btn.Position = UDim2.new(0, 10, 0, 50 + (i - 1) * 45)
    btn.Size = UDim2.new(1, -20, 0, 38)
    btn.Font = Enum.Font.SourceSansBold
    btn.Text = cmdText
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 14

    btn.MouseButton1Click:Connect(function()
        pcall(function()
            warn("Executed Command: " .. cmdText)
        end)
        btn.Text = "تم تنفيذ: " .. cmdText
        btn.BackgroundColor3 = Color3.fromRGB(30, 130, 30)
    end)
end

local TargetSearchBox = Instance.new("TextBox")
TargetSearchBox.Name = "TargetSearchBox"
TargetSearchBox.Parent = TargetP
TargetSearchBox.BackgroundColor3 = Color3.fromRGB(30, 50, 35)
TargetSearchBox.BorderColor3 = Color3.fromRGB(0, 180, 80)
TargetSearchBox.Position = UDim2.new(0, 10, 0, 10)
TargetSearchBox.Size = UDim2.new(1, -20, 0, 35)
TargetSearchBox.Font = Enum.Font.SourceSansBold
TargetSearchBox.PlaceholderText = "@target... (اكتب اسم الهدف واضغط Enter)"
TargetSearchBox.Text = ""
TargetSearchBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TargetSearchBox.TextSize = 13

local ProfileBoxTarget = Instance.new("Frame")
ProfileBoxTarget.Name = "ProfileBoxTarget"
ProfileBoxTarget.Parent = TargetP
ProfileBoxTarget.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
ProfileBoxTarget.BorderColor3 = Color3.fromRGB(0, 180, 80)
ProfileBoxTarget.Position = UDim2.new(0, 10, 0, 55)
ProfileBoxTarget.Size = UDim2.new(0, 120, 0, 90)

local TargetAvatar = Instance.new("ImageLabel")
TargetAvatar.Name = "TargetAvatar"
TargetAvatar.Parent = ProfileBoxTarget
TargetAvatar.BackgroundTransparency = 1
TargetAvatar.Size = UDim2.new(1, 0, 1, 0)
TargetAvatar.Image = Players:GetUserThumbnailAsync(localPlayer.UserId, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size420x420)

local TargetInfoLabel = Instance.new("TextLabel")
TargetInfoLabel.Name = "TargetInfoLabel"
TargetInfoLabel.Parent = TargetP
TargetInfoLabel.BackgroundTransparency = 1
TargetInfoLabel.Position = UDim2.new(0, 135, 0, 55)
TargetInfoLabel.Size = UDim2.new(1, -145, 0, 90)
TargetInfoLabel.Font = Enum.Font.SourceSansBold
TargetInfoLabel.Text = "UserID: -\nDisplay: -\nStatus: بانتظار كتابة الاسم..."
TargetInfoLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
TargetInfoLabel.TextSize = 11
TargetInfoLabel.TextXAlignment = Enum.TextXAlignment.Left
TargetInfoLabel.TextYAlignment = Enum.TextYAlignment.Top

local currentTarget = nil
local activeLoopConnection = nil
local timerLoopConnection = nil
local currentActiveBtn = nil
local targetStartTime = 0

local function formatDuration(totalSeconds)
    local days = math.floor(totalSeconds / 86400)
    local hours = math.floor((totalSeconds % 86400) / 3600)
    local minutes = math.floor((totalSeconds % 3600) / 60)
    local seconds = totalSeconds % 60

    local parts = {}
    if days > 0 then table.insert(parts, days .. " يوم") end
    if hours > 0 then table.insert(parts, hours .. " ساعة") end
    if minutes > 0 then table.insert(parts, minutes .. " دقيقة") end
    table.insert(parts, seconds .. " ثانية")

    return table.concat(parts, " و ")
end

TargetSearchBox.FocusLost:Connect(function()
    local query = TargetSearchBox.Text:lower()
    if query == "" then return end
    
    local foundPlayer = nil
    for _, p in ipairs(Players:GetPlayers()) do
        if p ~= localPlayer and (p.Name:lower():sub(1, #query) == query or p.DisplayName:lower():sub(1, #query) == query or p.Name:lower():find(query)) then
            foundPlayer = p
            break
        end
    end
    
    if foundPlayer then
        currentTarget = foundPlayer
        targetStartTime = os.time()
        TargetAvatar.Image = Players:GetUserThumbnailAsync(foundPlayer.UserId, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size420x420)
        
        if timerLoopConnection then
            timerLoopConnection:Disconnect()
            timerLoopConnection = nil
        end
        
        timerLoopConnection = RunService.Heartbeat:Connect(function()
            if currentTarget and currentTarget.Parent then
                local elapsed = os.time() - targetStartTime
                TargetInfoLabel.Text = "UserID: " .. currentTarget.UserId .. "\nDisplay: " .. currentTarget.DisplayName .. "\nالاسم: " .. currentTarget.Name .. "\nمتواجد منذ: " .. formatDuration(elapsed)
            end
        end)
        
        foundPlayer.AncestryChanged:Connect(function(_, parent)
            if not parent and currentTarget == foundPlayer then
                if timerLoopConnection then
                    timerLoopConnection:Disconnect()
                    timerLoopConnection = nil
                end
                local durationSec = os.time() - targetStartTime
                local formattedTime = formatDuration(durationSec)
                TargetInfoLabel.Text = "Status: طلع " .. foundPlayer.Name .. " من الجيم!\nمدة صمود الجلسة: " .. formattedTime
                currentTarget = nil
                if activeLoopConnection then
                    activeLoopConnection:Disconnect()
                    activeLoopConnection = nil
                end
            end
        end)
    else
        TargetInfoLabel.Text = "UserID: -\nDisplay: -\nStatus: لم يتم العثور على اللاعب!"
    end
end)

local UnviewBtn = Instance.new("TextButton")
UnviewBtn.Name = "UnviewBtn"
UnviewBtn.Parent = TargetP
UnviewBtn.BackgroundColor3 = Color3.fromRGB(150, 50, 0)
UnviewBtn.BorderColor3 = Color3.fromRGB(200, 80, 0)
UnviewBtn.Position = UDim2.new(0, 10, 0, 155)
UnviewBtn.Size = UDim2.new(1, -20, 0, 30)
UnviewBtn.Font = Enum.Font.SourceSansBold
UnviewBtn.Text = "إلغاء المشاهدة (إرجاع الكاميرا)"
UnviewBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
UnviewBtn.TextSize = 13

UnviewBtn.MouseButton1Click:Connect(function()
    if localPlayer.Character and localPlayer.Character:FindFirstChildOfClass("Humanoid") then
        workspace.CurrentCamera.CameraSubject = localPlayer.Character:FindFirstChildOfClass("Humanoid")
        TargetInfoLabel.Text = "Status: تم إرجاع الكاميرا لشخصيتك."
    end
end)

local targetActions = {
    {"مشاهدة", 0, 195},
    {"بانق عكسي", 1, 195},
    {"سوهآ عليه (Realistic)", 0, 240},
    {"بانق V1", 1, 240},
    {"بانق V2", 0, 285},
    {"متابعة (Smooth)", 1, 285},
    {"تثبيت", 0, 330}
}

for _, action in ipairs(targetActions) do
    local actName = action[1]
    local btn = Instance.new("TextButton")
    btn.Name = "ActionBtn_" .. actName
    btn.Parent = TargetP
    btn.BackgroundColor3 = Color3.fromRGB(30, 80, 50)
    btn.BorderColor3 = Color3.fromRGB(0, 180, 80)
    btn.Position = UDim2.new(action[2] * 0.5, action[2] == 0 and 10 or 5, 0, action[3])
    btn.Size = UDim2.new(0.5, -15, 0, 38)
    btn.Font = Enum.Font.SourceSansBold
    btn.Text = actName
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextSize = 13

    btn.MouseButton1Click:Connect(function()
        if not currentTarget then
            TargetInfoLabel.Text = "يرجى تحديد الهدف أولاً!"
            return
        end

        if activeLoopConnection then
            activeLoopConnection:Disconnect()
            activeLoopConnection = nil
        end

        if actName == "مشاهدة" then
            if currentTarget.Character and currentTarget.Character:FindFirstChildOfClass("Humanoid") then
                workspace.CurrentCamera.CameraSubject = currentTarget.Character:FindFirstChildOfClass("Humanoid")
            end
        else
            if currentActiveBtn == btn then
                currentActiveBtn = nil
                btn.BackgroundColor3 = Color3.fromRGB(30, 80, 50)
                btn.Text = actName
            else
                currentActiveBtn = btn
                btn.BackgroundColor3 = Color3.fromRGB(180, 30, 30)
                btn.Text = "إيقاف " .. actName

                local stepCounter = 0
                activeLoopConnection = RunService.RenderStepped:Connect(function()
                    if not currentTarget or not currentTarget.Character or not currentTarget.Character:FindFirstChild("HumanoidRootPart") then
                        return
                    end
                    
                    local targetHRP = currentTarget.Character.HumanoidRootPart
                    local myChar = localPlayer.Character
                    local myHRP = myChar and myChar:FindFirstChild("HumanoidRootPart")
                    local myHum = myChar and myChar:FindFirstChildOfClass("Humanoid")
                    
                    if myHRP then
                        stepCounter = stepCounter + 0.15
                        local targetCFrame = targetHRP.CFrame
                        local desiredCFrame = targetCFrame
                        
                        if actName == "سوهآ عليه (Realistic)" then
                            local walkOffset = math.sin(stepCounter) * 0.4
                            desiredCFrame = targetCFrame * CFrame.new(walkOffset, 0, 1.1)
                            if myHum then myHum:ChangeState(Enum.HumanoidStateType.Running) end
                        elseif actName == "متابعة (Smooth)" then
                            desiredCFrame = targetCFrame * CFrame.new(0, 0, 2)
                        elseif actName == "تثبيت" then
                            desiredCFrame = targetCFrame * CFrame.new(0, -1.2, -1.1) * CFrame.Angles(0, math.pi, 0)
                        elseif actName == "بانق V1" then
                            desiredCFrame = targetCFrame * CFrame.new(0, 0, 1.3)
                        elseif actName == "بانق V2" or actName == "بانق عكسي" then
                            desiredCFrame = targetCFrame * CFrame.new(0, 0, -1.3) * CFrame.Angles(0, math.pi, 0)
                        end
                        
                        myHRP.CFrame = myHRP.CFrame:Lerp(desiredCFrame, 0.35)
                        myHRP.Velocity = Vector3.new(0, 0, 0)
                        myHRP.RotVelocity = Vector3.new(0, 0, 0)
                    end
                end)
            end
        end
    end)
end

local TrackerSearchBox = Instance.new("TextBox")
TrackerSearchBox.Name = "TrackerSearchBox"
TrackerSearchBox.Parent = TrackerP
TrackerSearchBox.BackgroundColor3 = Color3.fromRGB(30, 50, 35)
TrackerSearchBox.BorderColor3 = Color3.fromRGB(0, 180, 80)
TrackerSearchBox.Position = UDim2.new(0, 10, 0, 10)
TrackerSearchBox.Size = UDim2.new(1, -20, 0, 35)
TrackerSearchBox.Font = Enum.Font.SourceSansBold
TrackerSearchBox.PlaceholderText = "@target... (اكتب أول حروف اسم اللاعب واضغط Enter)"
TrackerSearchBox.Text = ""
TrackerSearchBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TrackerSearchBox.TextSize = 13

local CardsContainer = Instance.new("ScrollingFrame")
CardsContainer.Name = "CardsContainer"
CardsContainer.Parent = TrackerP
CardsContainer.BackgroundTransparency = 1
CardsContainer.Position = UDim2.new(0, 10, 0, 55)
CardsContainer.Size = UDim2.new(1, -20, 1, -65)
CardsContainer.CanvasSize = UDim2.new(0, 0, 0, 0)
CardsContainer.ScrollBarThickness = 4

local CardsLayout = Instance.new("UIListLayout")
CardsLayout.Parent = CardsContainer
CardsLayout.SortOrder = Enum.SortOrder.LayoutOrder
CardsLayout.Padding = UDim.new(0, 8)

CardsLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
    CardsContainer.CanvasSize = UDim2.new(0, 0, 0, CardsLayout.AbsoluteContentSize.Y + 10)
end)

local trackedPlayers = {}

local function formatDetailedDuration(totalSec)
    local days = math.floor(totalSec / 86400)
    local hours = math.floor((totalSec % 86400) / 3600)
    local minutes = math.floor((totalSec % 3600) / 60)
    local seconds = totalSec % 60

    if days > 0 then
        return string.format("%d يوم %02d:%02d:%02d", days, hours, minutes, seconds)
    elseif hours > 0 then
        return string.format("%02d:%02d:%02d", hours, minutes, seconds)
    else
        return string.format("%02d:%02d", minutes, seconds)
    end
end

TrackerSearchBox.FocusLost:Connect(function(enterPressed)
    if not enterPressed then return end
    local query = TrackerSearchBox.Text:lower():gsub("%s+", "")
    if query == "" then return end
    TrackerSearchBox.Text = ""

    local targetPlr = nil
    for _, p in ipairs(Players:GetPlayers()) do
        if p ~= localPlayer and (p.Name:lower():sub(1, #query) == query or p.DisplayName:lower():sub(1, #query) == query or p.Name:lower():find(query)) then
            targetPlr = p
            break
        end
    end

    if targetPlr and not trackedPlayers[targetPlr.UserId] then
        local card = Instance.new("Frame")
        card.Name = "Card_" .. targetPlr.UserId
        card.Parent = CardsContainer
        card.BackgroundColor3 = Color3.fromRGB(120, 15, 15)
        card.BorderColor3 = Color3.fromRGB(180, 0, 0)
        card.Size = UDim2.new(1, 0, 0, 85)

        local avatar = Instance.new("ImageLabel")
        avatar.Name = "Avatar"
        avatar.Parent = card
        avatar.BackgroundTransparency = 1
        avatar.Position = UDim2.new(0, 5, 0, 5)
        avatar.Size = UDim2.new(0, 75, 0, 75)
        avatar.Image = Players:GetUserThumbnailAsync(targetPlr.UserId, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size420x420)

        local nameLbl = Instance.new("TextLabel")
        nameLbl.Name = "NameLbl"
        nameLbl.Parent = card
        nameLbl.BackgroundTransparency = 1
        nameLbl.Position = UDim2.new(0, 85, 0, 5)
        nameLbl.Size = UDim2.new(0, 140, 0, 20)
        nameLbl.Font = Enum.Font.SourceSansBold
        nameLbl.Text = targetPlr.Name
        nameLbl.TextColor3 = Color3.fromRGB(255, 255, 255)
        nameLbl.TextSize = 13
        nameLbl.TextXAlignment = Enum.TextXAlignment.Left

        local joinCountLbl = Instance.new("TextLabel")
        joinCountLbl.Name = "JoinCountLbl"
        joinCountLbl.Parent = card
        joinCountLbl.BackgroundTransparency = 1
        joinCountLbl.Position = UDim2.new(0, 225, 0, 5)
        joinCountLbl.Size = UDim2.new(0, 130, 0, 20)
        joinCountLbl.Font = Enum.Font.SourceSansBold
        joinCountLbl.Text = "عدد الدخول: 0"
        joinCountLbl.TextColor3 = Color3.fromRGB(0, 255, 100)
        joinCountLbl.TextSize = 12
        joinCountLbl.TextXAlignment = Enum.TextXAlignment.Left

        local leaveCountLbl = Instance.new("TextLabel")
        leaveCountLbl.Name = "LeaveCountLbl"
        leaveCountLbl.Parent = card
        leaveCountLbl.BackgroundTransparency = 1
        leaveCountLbl.Position = UDim2.new(0, 225, 0, 30)
        leaveCountLbl.Size = UDim2.new(0, 130, 0, 20)
        leaveCountLbl.Font = Enum.Font.SourceSansBold
        leaveCountLbl.Text = "عدد الخروج: 0"
        leaveCountLbl.TextColor3 = Color3.fromRGB(255, 100, 100)
        leaveCountLbl.TextSize = 12
        leaveCountLbl.TextXAlignment = Enum.TextXAlignment.Left

        local timerLbl = Instance.new("TextLabel")
        timerLbl.Name = "TimerLbl"
        timerLbl.Parent = card
        timerLbl.BackgroundTransparency = 1
        timerLbl.Position = UDim2.new(0, 85, 0, 50)
        timerLbl.Size = UDim2.new(0, 260, 0, 30)
        timerLbl.Font = Enum.Font.SourceSansBold
        timerLbl.Text = "00:00"
        timerLbl.TextColor3 = Color3.fromRGB(255, 255, 255)
        timerLbl.TextSize = 16
        timerLbl.TextXAlignment = Enum.TextXAlignment.Left

        local delBtn = Instance.new("TextButton")
        delBtn.Name = "DeleteBtn"
        delBtn.Parent = card
        delBtn.BackgroundColor3 = Color3.fromRGB(180, 20, 20)
        delBtn.BorderColor3 = Color3.fromRGB(255, 255, 255)
        delBtn.Position = UDim2.new(1, -35, 0, 10)
        delBtn.Size = UDim2.new(0, 25, 0, 28)
        delBtn.Font = Enum.Font.SourceSansBold
        delBtn.Text = "X"
        delBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
        delBtn.TextSize = 12

        local resetBtn = Instance.new("TextButton")
        resetBtn.Name = "ResetBtn"
        resetBtn.Parent = card
        resetBtn.BackgroundColor3 = Color3.fromRGB(20, 150, 50)
        resetBtn.BorderColor3 = Color3.fromRGB(255, 255, 255)
        resetBtn.Position = UDim2.new(1, -35, 0, 45)
        resetBtn.Size = UDim2.new(0, 25, 0, 28)
        resetBtn.Font = Enum.Font.SourceSansBold
        resetBtn.Text = "C"
        resetBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
        resetBtn.TextSize = 12

        local data = {
            player = targetPlr,
            userId = targetPlr.UserId,
            card = card,
            joins = 0,
            leaves = 0,
            accumulatedSec = 0,
            lastStartTime = os.time(),
            isOnline = true
        }

        delBtn.MouseButton1Click:Connect(function()
            card:Destroy()
            trackedPlayers[targetPlr.UserId] = nil
        end)

        resetBtn.MouseButton1Click:Connect(function()
            data.joins = 0
            data.leaves = 0
            data.accumulatedSec = 0
            data.lastStartTime = os.time()
            joinCountLbl.Text = "عدد الدخول: 0"
            leaveCountLbl.Text = "عدد الخروج: 0"
            timerLbl.Text = "00:00"
        end)

        trackedPlayers[targetPlr.UserId] = data

        targetPlr.AncestryChanged:Connect(function(_, parent)
            if not parent and trackedPlayers[targetPlr.UserId] then
                data.leaves = data.leaves + 1
                data.accumulatedSec = data.accumulatedSec + (os.time() - data.lastStartTime)
                data.isOnline = false
                leaveCountLbl.Text = "عدد الخروج: " .. data.leaves
                timerLbl.Text = formatDetailedDuration(data.accumulatedSec) .. " (متوقف)"
            end
        end)
    end
end)

Players.PlayerAdded:Connect(function(plr)
    local data = trackedPlayers[plr.UserId]
    if data then
        data.joins = data.joins + 1
        data.lastStartTime = os.time()
        data.isOnline = true
        data.player = plr
        
        if data.card and data.card.Parent then
            local joinLbl = data.card:FindFirstChild("JoinCountLbl")
            if joinLbl then joinLbl.Text = "عدد الدخول: " .. data.joins end
        end

        plr.AncestryChanged:Connect(function(_, parent)
            if not parent and trackedPlayers[plr.UserId] then
                data.leaves = data.leaves + 1
                data.accumulatedSec = data.accumulatedSec + (os.time() - data.lastStartTime)
                data.isOnline = false
                
                if data.card and data.card.Parent then
                    local leaveLbl = data.card:FindFirstChild("LeaveCountLbl")
                    local timerLbl = data.card:FindFirstChild("TimerLbl")
                    if leaveLbl then leaveLbl.Text = "عدد الخروج: " .. data.leaves end
                    if timerLbl then timerLbl.Text = formatDetailedDuration(data.accumulatedSec) .. " (متوقف)" end
                end
            end
        end)
    end
end)

RunService.Heartbeat:Connect(function()
    for _, data in pairs(trackedPlayers) do
        if data.isOnline and data.card and data.card.Parent then
            local currentTotal = data.accumulatedSec + (os.time() - data.lastStartTime)
            local timerLbl = data.card:FindFirstChild("TimerLbl")
            if timerLbl then
                timerLbl.Text = formatDetailedDuration(currentTotal)
            end
        end
    end
end)

local ToggleButton = Instance.new("TextButton")
ToggleButton.Name = "ToggleButton"
ToggleButton.Parent = ScreenGui
ToggleButton.BackgroundColor3 = Color3.fromRGB(30, 30, 35)
ToggleButton.BorderSizePixel = 0
ToggleButton.Position = UDim2.new(0, 25, 0.45, 0)
ToggleButton.Size = UDim2.new(0, 150, 0, 42)
ToggleButton.ZIndex = 20
ToggleButton.Font = Enum.Font.GothamBold
ToggleButton.Text = "فتح الواجهة"
ToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ToggleButton.TextSize = 13
ToggleButton.Active = true
ToggleButton.Draggable = true
ToggleButton.Visible = false

local ToggleCorner = Instance.new("UICorner")
ToggleCorner.CornerRadius = UDim.new(0, 21)
ToggleCorner.Parent = ToggleButton

local ToggleStroke = Instance.new("UIStroke")
ToggleStroke.Parent = ToggleButton
ToggleStroke.Color = Color3.fromRGB(220, 20, 20)
ToggleStroke.Thickness = 2
ToggleStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border

local ToggleGradient = Instance.new("UIGradient")
ToggleGradient.Parent = ToggleButton
ToggleGradient.Color = ColorSequence.new({
    ColorSequenceKeypoint.new(0, Color3.fromRGB(160, 15, 15)),
    ColorSequenceKeypoint.new(0.5, Color3.fromRGB(80, 10, 10)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(25, 25, 30))
})
ToggleGradient.Rotation = 45

local uiVisible = false

task.spawn(function()
    task.wait(5)
    if MainFrame and MainFrame.Parent then
        MainFrame.Visible = true
        uiVisible = true
    end
    if ToggleButton and ToggleButton.Parent then
        ToggleButton.Visible = true
        ToggleButton.Text = "نيتروس / كبيرهم"
        ToggleStroke.Color = Color3.fromRGB(220, 20, 20)
    end
end)

ToggleButton.MouseButton1Click:Connect(function()
    uiVisible = not uiVisible
    MainFrame.Visible = uiVisible
    if uiVisible then
        ToggleStroke.Color = Color3.fromRGB(220, 20, 20)
        ToggleButton.Text = "نيتروس / كبيرهم"
    else
        ToggleStroke.Color = Color3.fromRGB(80, 80, 80)
        ToggleButton.Text = "فتح الواجهة"
    end
end)
