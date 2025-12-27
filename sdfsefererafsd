


-- // https://cdn.discordapp.com/attachments/1376570652869398539/1451670535330205737/caption.gif?ex=6950e84a&is=694f96ca&hm=d897890d8e30c2bd86393b5799a9b2085958c99770412ff196a4893b0f61e678&






















































































































































































if (LPH_OBFUSCATED ~= nil) then
else
    function LPH_NO_VIRTUALIZE(a)
        return a
    end
    function LPH_JIT(a)
        return a
    end
    function LPH_JIT_MAX(a)
        return a
    end
    function LPH_CRASH()
    end
end
if (LRM_SEND_WEBHOOK ~= nil) then
else
    function LRM_SEND_WEBHOOK(b, c)
        return false
    end
end
if (LRM_SANITIZE ~= nil) then
else
    function LRM_SANITIZE(d, e)
        return tostring(d)
    end
end
local f = {
    UILibrary = function()
        local g = game:GetService("UserInputService")
        local h = game:GetService("TextService")
        local i = game:GetService("CoreGui")
        local j = game:GetService("Teams")
        local k = game:GetService("Players")
        local l = game:GetService("RunService")
        local m = game:GetService("TweenService")
        local n = l["RenderStepped"]
        local o = k["LocalPlayer"]
        local p = o:GetMouse()
        local q = protectgui or (syn and syn["protect_gui"]) or function()
            end
        local r = Instance.new("ScreenGui")
        q(r)
        r["ZIndexBehavior"] = Enum["ZIndexBehavior"]["Global"]
        r["Parent"] = i
        local Toggles = {}
        local Options = {}
        getgenv()["Toggles"] = Toggles
        getgenv()["Options"] = Options
        local s = {
            Registry = {},
            RegistryMap = {},
            HudRegistry = {},
            FontColor = Color3.fromRGB(255, 255, 255),
            MainColor = Color3.fromRGB(28, 28, 28),
            BackgroundColor = Color3.fromRGB(20, 20, 20),
            AccentColor = Color3.fromRGB(0, 85, 255),
            OutlineColor = Color3.fromRGB(50, 50, 50),
            RiskColor = Color3.fromRGB(255, 50, 50),
            Black = Color3.new(0, 0, 0),
            Font = Enum["Font"]["Code"],
            OpenedFrames = {},
            DependencyBoxes = {},
            Signals = {},
            ScreenGui = r
        }
        local t = 0
        task.spawn(
            function()
                while true do
                    task.wait(1 / 60)
                    t = t + (1 / 400)
                    if ((t > 1) or (4593 <= 2672)) then
                        t = 0
                    end
                    s["CurrentRainbowHue"] = t
                    s["CurrentRainbowColor"] = Color3.fromHSV(t, 0.8, 1)
                end
            end
        )
        local function u()
            local v = k:GetPlayers()
            for w = 1, #v do
                v[w] = v[w]["Name"]
            end
            table.sort(
                v,
                function(x, y)
                    return x < y
                end
            )
            return v
        end
        local function z()
            local A = j:GetTeams()
            for w = 1, #A do
                A[w] = A[w]["Name"]
            end
            table.sort(
                A,
                function(x, y)
                    return x < y
                end
            )
            return A
        end
        s.SafeCallback = function(self, a, ...)
            if not a then
                return
            end
            if not s["NotifyOnError"] then

            end
            local B, C = pcall(a, ...)
            if (not B or (1168 > 3156)) then
                local D, w = C:find(":%d+: ")
                if not w then
                    return s:Notify(C)
                end
                return s:Notify(C:sub(w + 1), 3)
            end
        end
        s.AttemptSave = function(self)
            if s["SaveManager"] then
                s["SaveManager"]:Save()
            end
        end
        s.Create = function(self, E, F)
            local G = E
            if ((type(E) == "string") or (572 > 4486)) then
                G = Instance.new(E)
            end
            for H, I in next, F do
                G[H] = I
            end
            return G
        end
        s.ApplyTextStroke = function(self, J)
            J["TextStrokeTransparency"] = 1
            s:Create(
                "UIStroke",
                {Color = Color3.new(0, 0, 0), Thickness = 1, LineJoinMode = Enum["LineJoinMode"]["Miter"], Parent = J}
            )
        end
        s.CreateLabel = function(self, F, K)
            local G =
                s:Create(
                "TextLabel",
                {
                    BackgroundTransparency = 1,
                    Font = s["Font"],
                    TextColor3 = s["FontColor"],
                    TextSize = 16,
                    TextStrokeTransparency = 0
                }
            )
            s:ApplyTextStroke(G)
            s:AddToRegistry(G, {TextColor3 = "FontColor"}, K)
            return s:Create(G, F)
        end
        s.MakeDraggable = function(self, Instance, L)
            Instance["Active"] = true
            Instance["InputBegan"]:Connect(
                function(M)
                    if ((1404 == 1404) and (M["UserInputType"] == Enum["UserInputType"]["MouseButton1"])) then
                        local N =
                            Vector2.new(
                            p["X"] - Instance["AbsolutePosition"]["X"],
                            p["Y"] - Instance["AbsolutePosition"]["Y"]
                        )
                        if (N["Y"] <= (L or 40)) then
                        else
                            return
                        end
                        while g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1) do
                            Instance["Position"] =
                                UDim2.new(
                                0,
                                (p["X"] - N["X"]) + (Instance["Size"]["X"]["Offset"] * Instance["AnchorPoint"]["X"]),
                                0,
                                (p["Y"] - N["Y"]) + (Instance["Size"]["Y"]["Offset"] * Instance["AnchorPoint"]["Y"])
                            )
                            n:Wait()
                        end
                    end
                end
            )
        end
        s.AddToolTip = function(self, O, P)
            local Q, R = s:GetTextBounds(O, s.Font, 14)
            local S =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["OutlineColor"],
                    Size = UDim2.fromOffset(Q + 5, R + 4),
                    ZIndex = 100,
                    Parent = s["ScreenGui"],
                    Visible = false
                }
            )
            local T =
                s:CreateLabel(
                {
                    Position = UDim2.fromOffset(3, 1),
                    Size = UDim2.fromOffset(Q, R),
                    TextSize = 14,
                    Text = O,
                    TextColor3 = s["FontColor"],
                    TextXAlignment = Enum["TextXAlignment"]["Left"],
                    ZIndex = (S["ZIndex"] + 1),
                    Parent = S
                }
            )
            s:AddToRegistry(S, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
            s:AddToRegistry(T, {TextColor3 = "FontColor"})
            local U = false
            P["MouseEnter"]:Connect(
                function()
                    if s:MouseIsOverOpenedFrame() then
                        return
                    end
                    U = true
                    S["Position"] = UDim2.fromOffset(p["X"] + 15, p["Y"] + 12)
                    S["Visible"] = true
                    while U do
                        l["Heartbeat"]:Wait()
                        S["Position"] = UDim2.fromOffset(p["X"] + 15, p["Y"] + 12)
                    end
                end
            )
            P["MouseLeave"]:Connect(
                function()
                    U = false
                    S["Visible"] = false
                end
            )
        end
        s.OnHighlight = function(self, V, Instance, F, W)
            V["MouseEnter"]:Connect(
                function()
                    local X = s["RegistryMap"][Instance]
                    for H, Y in next, F do
                        Instance[H] = s[Y] or Y
                        if (X and X["Properties"][H]) then
                            X["Properties"][H] = Y
                        end
                    end
                end
            )
            V["MouseLeave"]:Connect(
                function()
                    local X = s["RegistryMap"][Instance]
                    for H, Y in next, W do
                        Instance[H] = s[Y] or Y
                        if ((X and X["Properties"][H]) or (3748 < 2212)) then
                            X["Properties"][H] = Y
                        end
                    end
                end
            )
        end
        s.MouseIsOverOpenedFrame = function(self)
            for Z, D in next, s["OpenedFrames"] do
                local _, a0 = Z["AbsolutePosition"], Z["AbsoluteSize"]
                if
                    ((p["X"] >= _["X"]) and (p["X"] <= (_["X"] + a0["X"])) and (p["Y"] >= _["Y"]) and
                        (p["Y"] <= (_["Y"] + a0["Y"])))
                 then
                    return true
                end
            end
        end
        s.IsMouseOverFrame = function(self, Z)
            local _, a0 = Z["AbsolutePosition"], Z["AbsoluteSize"]
            if
                (((p["X"] >= _["X"]) and (p["X"] <= (_["X"] + a0["X"])) and (p["Y"] >= _["Y"]) and
                    (p["Y"] <= (_["Y"] + a0["Y"]))) or
                    (1180 == 2180))
             then
                return true
            end
        end
        s.UpdateDependencyBoxes = function(self)
            for D, a1 in next, s["DependencyBoxes"] do
                a1:Update()
            end
        end
        s.MapValue = function(self, I, a2, a3, a4, a5)
            return ((1 - ((I - a2) / (a3 - a2))) * a4) + (((I - a2) / (a3 - a2)) * a5)
        end
        s.GetTextBounds = function(self, a6, a7, a8, a9)
            local aa = h:GetTextSize(a6, a8, a7, a9 or Vector2.new(1920, 1080))
            return aa["X"], aa["Y"]
        end
        s.GetDarkerColor = function(self, ab)
            local ac, ad, ae = Color3.toHSV(ab)
            return Color3.fromHSV(ac, ad, ae / 1.5)
        end
        s["AccentColorDark"] = s:GetDarkerColor(s.AccentColor)
        s.AddToRegistry = function(self, Instance, F, K)
            local af = #s["Registry"] + 1
            local ag = {Instance = Instance, Properties = F, Idx = af}
            table.insert(s.Registry, ag)
            s["RegistryMap"][Instance] = ag
            if K then
                table.insert(s.HudRegistry, ag)
            end
        end
        s.RemoveFromRegistry = function(self, Instance)
            local ag = s["RegistryMap"][Instance]
            if ((4090 < 4653) and ag) then
                for af = #s["Registry"], 1, -1 do
                    if (s["Registry"][af] ~= ag) then
                    else
                        table.remove(s.Registry, af)
                    end
                end
                for af = #s["HudRegistry"], 1, -1 do
                    if ((s["HudRegistry"][af] == ag) or (2652 < 196)) then
                        table.remove(s.HudRegistry, af)
                    end
                end
                s["RegistryMap"][Instance] = nil
            end
        end
        s.UpdateColorsUsingRegistry = function(self)
            for af, ah in next, s["Registry"] do
                for H, Y in next, ah["Properties"] do
                    if ((4135 < 4817) and (type(Y) == "string")) then
                        ah["Instance"][H] = s[Y]
                    elseif ((272 == 272) and (type(Y) == "function")) then
                        ah["Instance"][H] = Y()
                    end
                end
            end
        end
        s.GiveSignal = function(self, ai)
            table.insert(s.Signals, ai)
        end
        s.Unload = function(self)
            for af = #s["Signals"], 1, -1 do
                local aj = table.remove(s.Signals, af)
                aj:Disconnect()
            end
            if ((100 <= 3123) and s["OnUnload"]) then
                s.OnUnload()
            end
            r:Destroy()
        end
        s.OnUnload = function(self, ak)
            s["OnUnload"] = ak
        end
        s:GiveSignal(
            r["DescendantRemoving"]:Connect(
                function(Instance)
                    if s["RegistryMap"][Instance] then
                        s:RemoveFromRegistry(Instance)
                    end
                end
            )
        )
        local al = {}
        do
            local am = {}
            am.AddColorPicker = function(self, af, an)
                local ao = self["TextLabel"]
                assert(an.Default, "AddColorPicker: Missing default value.")
                local ap = {
                    Value = an["Default"],
                    Transparency = (an["Transparency"] or 0),
                    Type = "ColorPicker",
                    Title = (((type(an.Title) == "string") and an["Title"]) or "Color picker"),
                    Callback = (an["Callback"] or function(ab)
                        end)
                }
                ap.SetHSVFromRGB = function(self, ab)
                    local ac, ad, ae = Color3.toHSV(ab)
                    ap["Hue"] = ac
                    ap["Sat"] = ad
                    ap["Vib"] = ae
                end
                ap:SetHSVFromRGB(ap.Value)
                local aq =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = ap["Value"],
                        BorderColor3 = s:GetDarkerColor(ap.Value),
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(0, 28, 0, 14),
                        ZIndex = 10,
                        Parent = ao
                    }
                )
                local ar =
                    s:Create(
                    "ImageLabel",
                    {
                        BorderSizePixel = 0,
                        Size = UDim2.new(0, 27, 0, 13),
                        ZIndex = 9,
                        Image = "http://www.roblox.com/asset/?id=12977615774",
                        Visible = not (not an["Transparency"]),
                        Parent = aq
                    }
                )
                local as =
                    s:Create(
                    "Frame",
                    {
                        Name = "Color",
                        BackgroundColor3 = Color3.new(1, 1, 1),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Position = UDim2.fromOffset(aq["AbsolutePosition"].X, aq["AbsolutePosition"]["Y"] + 18),
                        Size = UDim2.fromOffset(230, (an["Transparency"] and 271) or 253),
                        Visible = false,
                        ZIndex = 15,
                        Parent = r
                    }
                )
                aq:GetPropertyChangedSignal("AbsolutePosition"):Connect(
                    function()
                        as["Position"] = UDim2.fromOffset(aq["AbsolutePosition"].X, aq["AbsolutePosition"]["Y"] + 18)
                    end
                )
                local at =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["BackgroundColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 16,
                        Parent = as
                    }
                )
                local au =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["AccentColor"],
                        BorderSizePixel = 0,
                        Size = UDim2.new(1, 0, 0, 2),
                        ZIndex = 17,
                        Parent = at
                    }
                )
                local av =
                    s:Create(
                    "Frame",
                    {
                        BorderColor3 = Color3.new(0, 0, 0),
                        Position = UDim2.new(0, 4, 0, 25),
                        Size = UDim2.new(0, 200, 0, 200),
                        ZIndex = 17,
                        Parent = at
                    }
                )
                local aw =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["BackgroundColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 18,
                        Parent = av
                    }
                )
                local ax =
                    s:Create(
                    "ImageLabel",
                    {
                        BorderSizePixel = 0,
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 18,
                        Image = "rbxassetid://4155801252",
                        Parent = aw
                    }
                )
                local ay =
                    s:Create(
                    "ImageLabel",
                    {
                        AnchorPoint = Vector2.new(0.5, 0.5),
                        Size = UDim2.new(0, 6, 0, 6),
                        BackgroundTransparency = 1,
                        Image = "http://www.roblox.com/asset/?id=9619665977",
                        ImageColor3 = Color3.new(0, 0, 0),
                        ZIndex = 19,
                        Parent = ax
                    }
                )
                local az =
                    s:Create(
                    "ImageLabel",
                    {
                        Size = UDim2.new(0, ay["Size"]["X"]["Offset"] - 2, 0, ay["Size"]["Y"]["Offset"] - 2),
                        Position = UDim2.new(0, 1, 0, 1),
                        BackgroundTransparency = 1,
                        Image = "http://www.roblox.com/asset/?id=9619665977",
                        ZIndex = 20,
                        Parent = ay
                    }
                )
                local aA =
                    s:Create(
                    "Frame",
                    {
                        BorderColor3 = Color3.new(0, 0, 0),
                        Position = UDim2.new(0, 208, 0, 25),
                        Size = UDim2.new(0, 15, 0, 200),
                        ZIndex = 17,
                        Parent = at
                    }
                )
                local aB =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(1, 1, 1),
                        BorderSizePixel = 0,
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 18,
                        Parent = aA
                    }
                )
                local aC =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(1, 1, 1),
                        AnchorPoint = Vector2.new(0, 0.5),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(1, 0, 0, 1),
                        ZIndex = 18,
                        Parent = aB
                    }
                )
                local aD =
                    s:Create(
                    "Frame",
                    {
                        BorderColor3 = Color3.new(0, 0, 0),
                        Position = UDim2.fromOffset(4, 228),
                        Size = UDim2.new(0.5, -6, 0, 20),
                        ZIndex = 18,
                        Parent = at
                    }
                )
                local aE =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 18,
                        Parent = aD
                    }
                )
                s:Create(
                    "UIGradient",
                    {
                        Color = ColorSequence.new(
                            {
                                ColorSequenceKeypoint.new(0, Color3.new(1, 1, 1)),
                                ColorSequenceKeypoint.new(1, Color3.fromRGB(212, 212, 212))
                            }
                        ),
                        Rotation = 90,
                        Parent = aE
                    }
                )
                local aF =
                    s:Create(
                    "TextBox",
                    {
                        BackgroundTransparency = 1,
                        Position = UDim2.new(0, 5, 0, 0),
                        Size = UDim2.new(1, -5, 1, 0),
                        Font = s["Font"],
                        PlaceholderColor3 = Color3.fromRGB(190, 190, 190),
                        PlaceholderText = "Hex color",
                        Text = "#FFFFFF",
                        TextColor3 = s["FontColor"],
                        TextSize = 14,
                        TextStrokeTransparency = 0,
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        ZIndex = 20,
                        Parent = aE
                    }
                )
                s:ApplyTextStroke(aF)
                local aG =
                    s:Create(
                    aD:Clone(),
                    {Position = UDim2.new(0.5, 2, 0, 228), Size = UDim2.new(0.5, -6, 0, 20), Parent = at}
                )
                local aH =
                    s:Create(
                    aG["Frame"]:FindFirstChild("TextBox"),
                    {Text = "255, 255, 255", PlaceholderText = "RGB color", TextColor3 = s["FontColor"]}
                )
                local aI, aJ, aK
                if an["Transparency"] then
                    aI =
                        s:Create(
                        "Frame",
                        {
                            BorderColor3 = Color3.new(0, 0, 0),
                            Position = UDim2.fromOffset(4, 251),
                            Size = UDim2.new(1, -8, 0, 15),
                            ZIndex = 19,
                            Parent = at
                        }
                    )
                    aJ =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = ap["Value"],
                            BorderColor3 = s["OutlineColor"],
                            BorderMode = Enum["BorderMode"]["Inset"],
                            Size = UDim2.new(1, 0, 1, 0),
                            ZIndex = 19,
                            Parent = aI
                        }
                    )
                    s:AddToRegistry(aJ, {BorderColor3 = "OutlineColor"})
                    s:Create(
                        "ImageLabel",
                        {
                            BackgroundTransparency = 1,
                            Size = UDim2.new(1, 0, 1, 0),
                            Image = "http://www.roblox.com/asset/?id=12978095818",
                            ZIndex = 20,
                            Parent = aJ
                        }
                    )
                    aK =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = Color3.new(1, 1, 1),
                            AnchorPoint = Vector2.new(0.5, 0),
                            BorderColor3 = Color3.new(0, 0, 0),
                            Size = UDim2.new(0, 1, 1, 0),
                            ZIndex = 21,
                            Parent = aJ
                        }
                    )
                end
                local aL =
                    s:CreateLabel(
                    {
                        Size = UDim2.new(1, 0, 0, 14),
                        Position = UDim2.fromOffset(5, 5),
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        TextSize = 14,
                        Text = ap["Title"],
                        TextWrapped = false,
                        ZIndex = 16,
                        Parent = at
                    }
                )
                local aM = {}
                do
                    aM["Options"] = {}
                    aM["Container"] =
                        s:Create("Frame", {BorderColor3 = Color3.new(), ZIndex = 14, Visible = false, Parent = r})
                    aM["Inner"] =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["BackgroundColor"],
                            BorderColor3 = s["OutlineColor"],
                            BorderMode = Enum["BorderMode"]["Inset"],
                            Size = UDim2.fromScale(1, 1),
                            ZIndex = 15,
                            Parent = aM["Container"]
                        }
                    )
                    s:Create(
                        "UIListLayout",
                        {
                            Name = "Layout",
                            FillDirection = Enum["FillDirection"]["Vertical"],
                            SortOrder = Enum["SortOrder"]["LayoutOrder"],
                            Parent = aM["Inner"]
                        }
                    )
                    s:Create("UIPadding", {Name = "Padding", PaddingLeft = UDim.new(0, 4), Parent = aM["Inner"]})
                    local function aN()
                        aM["Container"]["Position"] =
                            UDim2.fromOffset(
                            aq["AbsolutePosition"]["X"] + aq["AbsoluteSize"]["X"] + 4,
                            aq["AbsolutePosition"]["Y"] + 1
                        )
                    end
                    local function aO()
                        local aP = 60
                        for w, aQ in next, aM["Inner"]:GetChildren() do
                            if aQ:IsA("TextLabel") then
                                aP = math.max(aP, aQ["TextBounds"].X)
                            end
                        end
                        aM["Container"]["Size"] =
                            UDim2.fromOffset(aP + 8, aM["Inner"]["Layout"]["AbsoluteContentSize"]["Y"] + 4)
                    end
                    aq:GetPropertyChangedSignal("AbsolutePosition"):Connect(aN)
                    aM["Inner"]["Layout"]:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(aO)
                    task.spawn(aN)
                    task.spawn(aO)
                    s:AddToRegistry(aM.Inner, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                    aM.Show = function(self)
                        self["Container"]["Visible"] = true
                    end
                    aM.Hide = function(self)
                        self["Container"]["Visible"] = false
                    end
                    aM.AddOption = function(self, aR, ak)
                        if ((type(ak) ~= "function") or (1369 > 4987)) then
                            function ak()
                            end
                        end
                        local aS =
                            s:CreateLabel(
                            {
                                Active = false,
                                Size = UDim2.new(1, 0, 0, 15),
                                TextSize = 13,
                                Text = aR,
                                ZIndex = 16,
                                Parent = self["Inner"],
                                TextXAlignment = Enum["TextXAlignment"]["Left"]
                            }
                        )
                        s:OnHighlight(aS, aS, {TextColor3 = "AccentColor"}, {TextColor3 = "FontColor"})
                        aS["InputBegan"]:Connect(
                            function(M)
                                if ((M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) or (863 >= 4584)) then
                                    return
                                end
                                ak()
                            end
                        )
                    end
                    aM:AddOption(
                        "Copy color",
                        function()
                            s["ColorClipboard"] = ap["Value"]
                            s:Notify("Copied color!", 2)
                        end
                    )
                    aM:AddOption(
                        "Paste color",
                        function()
                            if (not s["ColorClipboard"] or (724 >= 1668)) then
                                return s:Notify("You have not copied a color!", 2)
                            end
                            ap:SetValueRGB(s.ColorClipboard)
                        end
                    )
                    aM:AddOption(
                        "Copy HEX",
                        function()
                            pcall(setclipboard, ap["Value"]:ToHex())
                            s:Notify("Copied hex code to clipboard!", 2)
                        end
                    )
                    aM:AddOption(
                        "Copy RGB",
                        function()
                            pcall(
                                setclipboard,
                                table.concat(
                                    {
                                        math.floor(ap["Value"]["R"] * 255),
                                        math.floor(ap["Value"]["G"] * 255),
                                        math.floor(ap["Value"]["B"] * 255)
                                    },
                                    ", "
                                )
                            )
                            s:Notify("Copied RGB values to clipboard!", 2)
                        end
                    )
                end
                s:AddToRegistry(at, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                s:AddToRegistry(au, {BackgroundColor3 = "AccentColor"})
                s:AddToRegistry(aw, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                s:AddToRegistry(aE, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                s:AddToRegistry(aG.Frame, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                s:AddToRegistry(aH, {TextColor3 = "FontColor"})
                s:AddToRegistry(aF, {TextColor3 = "FontColor"})
                local aT = {}
                for t = 0, 1, 0.1 do
                    table.insert(aT, ColorSequenceKeypoint.new(t, Color3.fromHSV(t, 1, 1)))
                end
                local aU = s:Create("UIGradient", {Color = ColorSequence.new(aT), Rotation = 90, Parent = aB})
                aF["FocusLost"]:Connect(
                    function(aV)
                        if aV then
                            local B, aW = pcall(Color3.fromHex, aF.Text)
                            if (B and (typeof(aW) == "Color3")) then
                                ap["Hue"], ap["Sat"], ap["Vib"] = Color3.toHSV(aW)
                            end
                        end
                        ap:Display()
                    end
                )
                aH["FocusLost"]:Connect(
                    function(aV)
                        if ((428 < 1804) and aV) then
                            local aX, aY, aZ = aH["Text"]:match("(%d+),%s*(%d+),%s*(%d+)")
                            if (aX and aY and aZ) then
                                ap["Hue"], ap["Sat"], ap["Vib"] = Color3.toHSV(Color3.fromRGB(aX, aY, aZ))
                            end
                        end
                        ap:Display()
                    end
                )
                ap.Display = function(self)
                    ap["Value"] = Color3.fromHSV(ap.Hue, ap.Sat, ap.Vib)
                    ax["BackgroundColor3"] = Color3.fromHSV(ap.Hue, 1, 1)
                    s:Create(
                        aq,
                        {
                            BackgroundColor3 = ap["Value"],
                            BackgroundTransparency = ap["Transparency"],
                            BorderColor3 = s:GetDarkerColor(ap.Value)
                        }
                    )
                    if (aJ or (3325 > 4613)) then
                        aJ["BackgroundColor3"] = ap["Value"]
                        aK["Position"] = UDim2.new(1 - ap["Transparency"], 0, 0, 0)
                    end
                    ay["Position"] = UDim2.new(ap.Sat, 0, 1 - ap["Vib"], 0)
                    aC["Position"] = UDim2.new(0, 0, ap.Hue, 0)
                    aF["Text"] = "#" .. ap["Value"]:ToHex()
                    aH["Text"] =
                        table.concat(
                        {
                            math.floor(ap["Value"]["R"] * 255),
                            math.floor(ap["Value"]["G"] * 255),
                            math.floor(ap["Value"]["B"] * 255)
                        },
                        ", "
                    )
                    s:SafeCallback(ap.Callback, ap.Value)
                    s:SafeCallback(ap.Changed, ap.Value)
                end
                ap.OnChanged = function(self, a_)
                    ap["Changed"] = a_
                    a_(ap.Value)
                end
                ap.Show = function(self)
                    for Z, b0 in next, s["OpenedFrames"] do
                        if (Z["Name"] ~= "Color") then
                        else
                            Z["Visible"] = false
                            s["OpenedFrames"][Z] = nil
                        end
                    end
                    as["Visible"] = true
                    s["OpenedFrames"][as] = true
                end
                ap.Hide = function(self)
                    as["Visible"] = false
                    s["OpenedFrames"][as] = nil
                end
                ap.SetValue = function(self, b1, b2)
                    local ab = Color3.fromHSV(b1[1], b1[2], b1[3])
                    ap["Transparency"] = b2 or 0
                    ap:SetHSVFromRGB(ab)
                    ap:Display()
                end
                ap.SetValueRGB = function(self, ab, b2)
                    ap["Transparency"] = b2 or 0
                    ap:SetHSVFromRGB(ab)
                    ap:Display()
                end
                ax["InputBegan"]:Connect(
                    function(M)
                        if (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) then
                        else
                            while g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1) do
                                local b3 = ax["AbsolutePosition"]["X"]
                                local b4 = b3 + ax["AbsoluteSize"]["X"]
                                local b5 = math.clamp(p.X, b3, b4)
                                local b6 = ax["AbsolutePosition"]["Y"]
                                local b7 = b6 + ax["AbsoluteSize"]["Y"]
                                local b8 = math.clamp(p.Y, b6, b7)
                                ap["Sat"] = (b5 - b3) / (b4 - b3)
                                ap["Vib"] = 1 - ((b8 - b6) / (b7 - b6))
                                ap:Display()
                                n:Wait()
                            end
                            s:AttemptSave()
                        end
                    end
                )
                aB["InputBegan"]:Connect(
                    function(M)
                        if ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) or (4950 <= 4553)) then
                            while g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1) do
                                local b6 = aB["AbsolutePosition"]["Y"]
                                local b7 = b6 + aB["AbsoluteSize"]["Y"]
                                local b8 = math.clamp(p.Y, b6, b7)
                                ap["Hue"] = (b8 - b6) / (b7 - b6)
                                ap:Display()
                                n:Wait()
                            end
                            s:AttemptSave()
                        end
                    end
                )
                aq["InputBegan"]:Connect(
                    function(M)
                        if
                            ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            if ((2665 <= 3933) and as["Visible"]) then
                                ap:Hide()
                            else
                                aM:Hide()
                                ap:Show()
                            end
                        elseif
                            ((3273 == 3273) and (M["UserInputType"] == Enum["UserInputType"]["MouseButton2"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            aM:Show()
                            ap:Hide()
                        end
                    end
                )
                if aJ then
                    aJ["InputBegan"]:Connect(
                        function(M)
                            if (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) then
                            else
                                while g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1) do
                                    local b3 = aJ["AbsolutePosition"]["X"]
                                    local b4 = b3 + aJ["AbsoluteSize"]["X"]
                                    local b5 = math.clamp(p.X, b3, b4)
                                    ap["Transparency"] = 1 - ((b5 - b3) / (b4 - b3))
                                    ap:Display()
                                    n:Wait()
                                end
                                s:AttemptSave()
                            end
                        end
                    )
                end
                s:GiveSignal(
                    g["InputBegan"]:Connect(
                        function(M, b9)
                            if ((3824 > 409) and (b9 or g:GetFocusedTextBox())) then
                                return
                            end
                            if (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) then
                            else
                                local _, a0 = as["AbsolutePosition"], as["AbsoluteSize"]
                                if
                                    ((2087 == 2087) and
                                        ((p["X"] < _["X"]) or (p["X"] > (_["X"] + a0["X"])) or
                                            (p["Y"] < ((_["Y"] - 20) - 1)) or
                                            (p["Y"] > (_["Y"] + a0["Y"]))))
                                 then
                                    ap:Hide()
                                end
                                if not s:IsMouseOverFrame(aM.Container) then
                                    aM:Hide()
                                end
                            end
                            if
                                ((M["UserInputType"] == Enum["UserInputType"]["MouseButton2"]) and
                                    aM["Container"]["Visible"])
                             then
                                if
                                    ((not s:IsMouseOverFrame(aM.Container) and not s:IsMouseOverFrame(aq)) or
                                        (3404 > 4503))
                                 then
                                    aM:Hide()
                                end
                            end
                        end
                    )
                )
                ap:Display()
                ap["DisplayFrame"] = aq
                Options[af] = ap
                return self
            end
            am.AddKeyPicker = function(self, af, an)
                local ba = self
                local ao = self["TextLabel"]
                local bb = self["Container"]
                assert(an.Default, "AddKeyPicker: Missing default value.")
                local bc = {
                    Value = an["Default"],
                    Toggled = false,
                    Mode = (an["Mode"] or "Toggle"),
                    Type = "KeyPicker",
                    Callback = (an["Callback"] or function(I)
                        end),
                    ChangedCallback = (an["ChangedCallback"] or function(bd)
                        end),
                    SyncToggleState = (an["SyncToggleState"] or false)
                }
                if (bc["SyncToggleState"] or (3506 <= 1309)) then
                    an["Modes"] = {"Toggle"}
                    an["Mode"] = "Toggle"
                end
                local be =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(0, 28, 0, 15),
                        ZIndex = 6,
                        Parent = ao
                    }
                )
                local bf =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["BackgroundColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 7,
                        Parent = be
                    }
                )
                s:AddToRegistry(bf, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                local aL =
                    s:CreateLabel(
                    {
                        Size = UDim2.new(1, 0, 1, 0),
                        TextSize = 13,
                        Text = an["Default"],
                        TextWrapped = true,
                        ZIndex = 8,
                        Parent = bf
                    }
                )
                local bg =
                    s:Create(
                    "Frame",
                    {
                        BorderColor3 = Color3.new(0, 0, 0),
                        Position = UDim2.fromOffset(
                            ao["AbsolutePosition"]["X"] + ao["AbsoluteSize"]["X"] + 4,
                            ao["AbsolutePosition"]["Y"] + 1
                        ),
                        Size = UDim2.new(0, 60, 0, 45 + 2),
                        Visible = false,
                        ZIndex = 14,
                        Parent = r
                    }
                )
                ao:GetPropertyChangedSignal("AbsolutePosition"):Connect(
                    function()
                        bg["Position"] =
                            UDim2.fromOffset(
                            ao["AbsolutePosition"]["X"] + ao["AbsoluteSize"]["X"] + 4,
                            ao["AbsolutePosition"]["Y"] + 1
                        )
                    end
                )
                local bh =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["BackgroundColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 15,
                        Parent = bg
                    }
                )
                s:AddToRegistry(bh, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                s:Create(
                    "UIListLayout",
                    {
                        FillDirection = Enum["FillDirection"]["Vertical"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        Parent = bh
                    }
                )
                local bi =
                    s:CreateLabel(
                    {
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        Size = UDim2.new(1, 0, 0, 18),
                        TextSize = 13,
                        Visible = false,
                        ZIndex = 110,
                        Parent = s["KeybindContainer"]
                    },
                    true
                )
                local bj = an["Modes"] or {"Always", "Toggle", "Hold"}
                local bk = {}
                for af, bl in next, bj do
                    local bm = {}
                    local T =
                        s:CreateLabel(
                        {
                            Active = false,
                            Size = UDim2.new(1, 0, 0, 15),
                            TextSize = 13,
                            Text = bl,
                            ZIndex = 16,
                            Parent = bh
                        }
                    )
                    bm.Select = function(self)
                        for D, aS in next, bk do
                            aS:Deselect()
                        end
                        bc["Mode"] = bl
                        T["TextColor3"] = s["AccentColor"]
                        s["RegistryMap"][T]["Properties"]["TextColor3"] = "AccentColor"
                        bg["Visible"] = false
                    end
                    bm.Deselect = function(self)
                        bc["Mode"] = nil
                        T["TextColor3"] = s["FontColor"]
                        s["RegistryMap"][T]["Properties"]["TextColor3"] = "FontColor"
                    end
                    T["InputBegan"]:Connect(
                        function(M)
                            if (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) then
                            else
                                bm:Select()
                                s:AttemptSave()
                            end
                        end
                    )
                    if (bl == bc["Mode"]) then
                        bm:Select()
                    end
                    bk[bl] = bm
                end
                bc.Update = function(self)
                    if ((2955 == 2955) and an["NoUI"]) then
                        return
                    end
                    local bn = bc:GetState()
                    bi["Text"] = string.format("[%s] %s (%s)", bc.Value, an.Text, bc.Mode)
                    bi["Visible"] = true
                    bi["TextColor3"] = (bn and s["AccentColor"]) or s["FontColor"]
                    s["RegistryMap"][bi]["Properties"]["TextColor3"] = (bn and "AccentColor") or "FontColor"
                    local bo = 0
                    local bp = 0
                    for D, T in next, s["KeybindContainer"]:GetChildren() do
                        if (T:IsA("TextLabel") and T["Visible"]) then
                            bo = bo + 18
                            if (T["TextBounds"]["X"] <= bp) then
                            else
                                bp = T["TextBounds"]["X"]
                            end
                        end
                    end
                    s["KeybindFrame"]["Size"] = UDim2.new(0, math.max(bp + 10, 210), 0, bo + 23)
                end
                bc.GetState = function(self)
                    if ((bc["Mode"] == "Always") or (2903 == 1495)) then
                        return true
                    elseif ((4546 >= 2275) and (bc["Mode"] == "Hold")) then
                        if (bc["Value"] ~= "None") then
                        else
                            return false
                        end
                        local bq = bc["Value"]
                        if ((bq == "MB1") or (bq == "MB2")) then
                            return ((bq == "MB1") and g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1)) or
                                ((bq == "MB2") and g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton2))
                        else
                            return g:IsKeyDown(Enum["KeyCode"][bc["Value"]])
                        end
                    else
                        if ((819 >= 22) and (ba["Type"] == "Toggle") and bc["SyncToggleState"]) then
                            return ba["Value"]
                        end
                        return bc["Toggled"]
                    end
                end
                bc.SetValue = function(self, ag)
                    local bq, bl = ag[1], ag[2]
                    aL["Text"] = bq
                    bc["Value"] = bq
                    bk[bl]:Select()
                    bc:Update()
                end
                bc.OnClick = function(self, ak)
                    bc["Clicked"] = ak
                end
                bc.OnChanged = function(self, ak)
                    bc["Changed"] = ak
                    ak(bc.Value)
                end
                if ba["Addons"] then
                    table.insert(ba.Addons, bc)
                end
                bc.DoClick = function(self)
                    if ((ba["Type"] == "Toggle") and bc["SyncToggleState"]) then
                        ba:SetValue(not ba["Value"])
                    end
                    s:SafeCallback(bc.Callback, bc.Toggled)
                    s:SafeCallback(bc.Clicked, bc.Toggled)
                end
                local br = false
                be["InputBegan"]:Connect(
                    function(M)
                        if
                            ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            br = true
                            aL["Text"] = ""
                            local bs
                            local a6 = ""
                            task.spawn(
                                function()
                                    while not bs do
                                        if ((3162 == 3162) and (a6 == "...")) then
                                            a6 = ""
                                        end
                                        a6 = a6 .. "."
                                        aL["Text"] = a6
                                        wait(0.4)
                                    end
                                end
                            )
                            wait(0.2)
                            local bt
                            bt =
                                g["InputBegan"]:Connect(
                                function(M)
                                    local bq
                                    if (M["UserInputType"] == Enum["UserInputType"]["Keyboard"]) then
                                        bq = M["KeyCode"]["Name"]
                                    elseif
                                        ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) or (2369 > 4429))
                                     then
                                        bq = "MB1"
                                    elseif (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton2"]) then
                                    else
                                        bq = "MB2"
                                    end
                                    bs = true
                                    br = false
                                    aL["Text"] = bq
                                    bc["Value"] = bq
                                    s:SafeCallback(bc.ChangedCallback, M["KeyCode"] or M["UserInputType"])
                                    s:SafeCallback(bc.Changed, M["KeyCode"] or M["UserInputType"])
                                    s:AttemptSave()
                                    bt:Disconnect()
                                end
                            )
                        elseif
                            ((M["UserInputType"] == Enum["UserInputType"]["MouseButton2"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            bg["Visible"] = true
                        end
                    end
                )
                s:GiveSignal(
                    g["InputBegan"]:Connect(
                        function(M, b9)
                            if (b9 or g:GetFocusedTextBox()) then
                                return
                            end
                            if not br then
                                if ((4095 >= 3183) and (bc["Mode"] == "Toggle")) then
                                    local bq = bc["Value"]
                                    if ((bq == "MB1") or (bq == "MB2")) then
                                        if
                                            (((bq == "MB1") and
                                                (M["UserInputType"] == Enum["UserInputType"]["MouseButton1"])) or
                                                ((bq == "MB2") and
                                                    (M["UserInputType"] == Enum["UserInputType"]["MouseButton2"])))
                                         then
                                            bc["Toggled"] = not bc["Toggled"]
                                            bc:DoClick()
                                        end
                                    elseif ((M["UserInputType"] == Enum["UserInputType"]["Keyboard"]) or (3711 < 1008)) then
                                        if (M["KeyCode"]["Name"] ~= bq) then
                                        else
                                            bc["Toggled"] = not bc["Toggled"]
                                            bc:DoClick()
                                        end
                                    end
                                end
                                bc:Update()
                            end
                            if ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) or (1049 <= 906)) then
                                local _, a0 = bg["AbsolutePosition"], bg["AbsoluteSize"]
                                if
                                    ((p["X"] < _["X"]) or (p["X"] > (_["X"] + a0["X"])) or
                                        (p["Y"] < ((_["Y"] - 20) - 1)) or
                                        (p["Y"] > (_["Y"] + a0["Y"])))
                                 then
                                    bg["Visible"] = false
                                end
                            end
                        end
                    )
                )
                s:GiveSignal(
                    g["InputEnded"]:Connect(
                        function(M, b9)
                            if (b9 or g:GetFocusedTextBox()) then
                                return
                            end
                            if not br then
                                bc:Update()
                            end
                        end
                    )
                )
                bc:Update()
                Options[af] = bc
                return self
            end
            al["__index"] = am
            al.__namecall = function(bu, bq, ...)
                return am[bq](...)
            end
        end
        local bv = {}
        do
            local am = {}
            am.AddBlank = function(self, a8)
                local bw = self
                local bb = bw["Container"]
                s:Create("Frame", {BackgroundTransparency = 1, Size = UDim2.new(1, 0, 0, a8), ZIndex = 1, Parent = bb})
            end
            am.AddLabel = function(self, a6, bx)
                local T = {}
                local bw = self
                local bb = bw["Container"]
                local by =
                    s:CreateLabel(
                    {
                        Size = UDim2.new(1, -4, 0, 15),
                        TextSize = 14,
                        Text = a6,
                        TextWrapped = (bx or false),
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                if ((4513 > 2726) and bx) then
                    local R = select(2, s:GetTextBounds(a6, s.Font, 14, Vector2.new(by["AbsoluteSize"].X, math.huge)))
                    by["Size"] = UDim2.new(1, -4, 0, R)
                else
                    s:Create(
                        "UIListLayout",
                        {
                            Padding = UDim.new(0, 4),
                            FillDirection = Enum["FillDirection"]["Horizontal"],
                            HorizontalAlignment = Enum["HorizontalAlignment"]["Right"],
                            SortOrder = Enum["SortOrder"]["LayoutOrder"],
                            Parent = by
                        }
                    )
                end
                T["TextLabel"] = by
                T["Container"] = bb
                T.SetText = function(self, a6)
                    by["Text"] = a6
                    if (bx or (1481 >= 2658)) then
                        local R =
                            select(2, s:GetTextBounds(a6, s.Font, 14, Vector2.new(by["AbsoluteSize"].X, math.huge)))
                        by["Size"] = UDim2.new(1, -4, 0, R)
                    end
                    bw:Resize()
                end
                if not bx then
                    setmetatable(T, al)
                end
                bw:AddBlank(5)
                bw:Resize()
                return T
            end
            am.AddButton = function(self, ...)
                local aS = {}
                local function bz(E, bA, ...)
                    local bB = select(1, ...)
                    if ((type(bB) == "table") or (3220 == 1364)) then
                        bA["Text"] = bB["Text"]
                        bA["Func"] = bB["Func"]
                        bA["DoubleClick"] = bB["DoubleClick"]
                        bA["Tooltip"] = bB["Tooltip"]
                    else
                        bA["Text"] = select(1, ...)
                        bA["Func"] = select(2, ...)
                    end
                    assert(type(bA.Func) == "function", "AddButton: `Func` callback is missing.")
                end
                bz("Button", aS, ...)
                local bw = self
                local bb = bw["Container"]
                local function bC(aS)
                    local bD =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = Color3.new(0, 0, 0),
                            BorderColor3 = Color3.new(0, 0, 0),
                            Size = UDim2.new(1, -4, 0, 20),
                            ZIndex = 5
                        }
                    )
                    local bE =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["MainColor"],
                            BorderColor3 = s["OutlineColor"],
                            BorderMode = Enum["BorderMode"]["Inset"],
                            Size = UDim2.new(1, 0, 1, 0),
                            ZIndex = 6,
                            Parent = bD
                        }
                    )
                    local T =
                        s:CreateLabel(
                        {Size = UDim2.new(1, 0, 1, 0), TextSize = 14, Text = aS["Text"], ZIndex = 6, Parent = bE}
                    )
                    s:Create(
                        "UIGradient",
                        {
                            Color = ColorSequence.new(
                                {
                                    ColorSequenceKeypoint.new(0, Color3.new(1, 1, 1)),
                                    ColorSequenceKeypoint.new(1, Color3.fromRGB(212, 212, 212))
                                }
                            ),
                            Rotation = 90,
                            Parent = bE
                        }
                    )
                    s:AddToRegistry(bD, {BorderColor3 = "Black"})
                    s:AddToRegistry(bE, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                    s:OnHighlight(bD, bD, {BorderColor3 = "AccentColor"}, {BorderColor3 = "Black"})
                    return bD, bE, T
                end
                local function bF(aS)
                    local function bG(C, bH, bI)
                        local bJ = Instance.new("BindableEvent")
                        local bK =
                            C:Once(
                            function(...)
                                if ((type(bI) == "function") and bI(...)) then
                                    bJ:Fire(true)
                                else
                                    bJ:Fire(false)
                                end
                            end
                        )
                        task.delay(
                            bH,
                            function()
                                bK:disconnect()
                                bJ:Fire(false)
                            end
                        )
                        return bJ["Event"]:Wait()
                    end
                    local function bL(M)
                        if s:MouseIsOverOpenedFrame() then
                            return false
                        end
                        if ((M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) or (1054 > 3392)) then
                            return false
                        end
                        return true
                    end
                    aS["Outer"]["InputBegan"]:Connect(
                        function(M)
                            if (not bL(M) or (676 >= 1642)) then
                                return
                            end
                            if aS["Locked"] then
                                return
                            end
                            if ((4136 > 2397) and aS["DoubleClick"]) then
                                s:RemoveFromRegistry(aS.Label)
                                s:AddToRegistry(aS.Label, {TextColor3 = "AccentColor"})
                                aS["Label"]["TextColor3"] = s["AccentColor"]
                                aS["Label"]["Text"] = "Are you sure?"
                                aS["Locked"] = true
                                local bM = bG(aS["Outer"].InputBegan, 0.5, bL)
                                s:RemoveFromRegistry(aS.Label)
                                s:AddToRegistry(aS.Label, {TextColor3 = "FontColor"})
                                aS["Label"]["TextColor3"] = s["FontColor"]
                                aS["Label"]["Text"] = aS["Text"]
                                task.defer(rawset, aS, "Locked", false)
                                if bM then
                                    s:SafeCallback(aS.Func)
                                end
                                return
                            end
                            s:SafeCallback(aS.Func)
                        end
                    )
                end
                aS["Outer"], aS["Inner"], aS["Label"] = bC(aS)
                aS["Outer"]["Parent"] = bb
                bF(aS)
                aS.AddTooltip = function(self, bN)
                    if (type(bN) ~= "string") then
                    else
                        s:AddToolTip(bN, self.Outer)
                    end
                    return self
                end
                aS.AddButton = function(self, ...)
                    local bO = {}
                    bz("SubButton", bO, ...)
                    self["Outer"]["Size"] = UDim2.new(0.5, -2, 0, 20)
                    bO["Outer"], bO["Inner"], bO["Label"] = bC(bO)
                    bO["Outer"]["Position"] = UDim2.new(1, 3, 0, 0)
                    bO["Outer"]["Size"] =
                        UDim2.fromOffset(self["Outer"]["AbsoluteSize"]["X"] - 2, self["Outer"]["AbsoluteSize"].Y)
                    bO["Outer"]["Parent"] = self["Outer"]
                    bO.AddTooltip = function(self, bN)
                        if ((type(bN) == "string") or (4334 == 4245)) then
                            s:AddToolTip(bN, self.Outer)
                        end
                        return bO
                    end
                    if (type(bO.Tooltip) == "string") then
                        bO:AddTooltip(bO.Tooltip)
                    end
                    bF(bO)
                    return bO
                end
                if ((type(aS.Tooltip) == "string") or (4276 <= 3031)) then
                    aS:AddTooltip(aS.Tooltip)
                end
                bw:AddBlank(5)
                bw:Resize()
                return aS
            end
            am.AddDivider = function(self)
                local bw = self
                local bb = self["Container"]
                local bP = {Type = "Divider"}
                bw:AddBlank(2)
                local bQ =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(1, -4, 0, 5),
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                local bR =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 6,
                        Parent = bQ
                    }
                )
                s:AddToRegistry(bQ, {BorderColor3 = "Black"})
                s:AddToRegistry(bR, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                bw:AddBlank(9)
                bw:Resize()
            end
            am.AddInput = function(self, af, an)
                assert(an.Text, "AddInput: Missing `Text` string.")
                local bS = {
                    Value = (an["Default"] or ""),
                    Numeric = (an["Numeric"] or false),
                    Finished = (an["Finished"] or false),
                    Type = "Input",
                    Callback = (an["Callback"] or function(I)
                        end)
                }
                local bw = self
                local bb = bw["Container"]
                local bT =
                    s:CreateLabel(
                    {
                        Size = UDim2.new(1, 0, 0, 15),
                        TextSize = 14,
                        Text = an["Text"],
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                bw:AddBlank(1)
                local bU =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(1, -4, 0, 20),
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                local bV =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 6,
                        Parent = bU
                    }
                )
                s:AddToRegistry(bV, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                s:OnHighlight(bU, bU, {BorderColor3 = "AccentColor"}, {BorderColor3 = "Black"})
                if ((type(an.Tooltip) == "string") or (4782 <= 1199)) then
                    s:AddToolTip(an.Tooltip, bU)
                end
                s:Create(
                    "UIGradient",
                    {
                        Color = ColorSequence.new(
                            {
                                ColorSequenceKeypoint.new(0, Color3.new(1, 1, 1)),
                                ColorSequenceKeypoint.new(1, Color3.fromRGB(212, 212, 212))
                            }
                        ),
                        Rotation = 90,
                        Parent = bV
                    }
                )
                local bb =
                    s:Create(
                    "Frame",
                    {
                        BackgroundTransparency = 1,
                        ClipsDescendants = true,
                        Position = UDim2.new(0, 5, 0, 0),
                        Size = UDim2.new(1, -5, 1, 0),
                        ZIndex = 7,
                        Parent = bV
                    }
                )
                local bW =
                    s:Create(
                    "TextBox",
                    {
                        BackgroundTransparency = 1,
                        Position = UDim2.fromOffset(0, 0),
                        Size = UDim2.fromScale(5, 1),
                        Font = s["Font"],
                        PlaceholderColor3 = Color3.fromRGB(190, 190, 190),
                        PlaceholderText = (an["Placeholder"] or ""),
                        Text = (an["Default"] or ""),
                        TextColor3 = s["FontColor"],
                        TextSize = 14,
                        TextStrokeTransparency = 0,
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        ZIndex = 7,
                        Parent = bb
                    }
                )
                s:ApplyTextStroke(bW)
                bS.SetValue = function(self, a6)
                    if ((an["MaxLength"] and (#a6 > an["MaxLength"])) or (4864 < 1902)) then
                        a6 = a6:sub(1, an.MaxLength)
                    end
                    if ((4839 >= 3700) and bS["Numeric"]) then
                        if ((not tonumber(a6) and (a6:len() > 0)) or (1075 > 1918)) then
                            a6 = bS["Value"]
                        end
                    end
                    bS["Value"] = a6
                    bW["Text"] = a6
                    s:SafeCallback(bS.Callback, bS.Value)
                    s:SafeCallback(bS.Changed, bS.Value)
                end
                if ((396 <= 3804) and bS["Finished"]) then
                    bW["FocusLost"]:Connect(
                        function(aV)
                            if not aV then
                                return
                            end
                            bS:SetValue(bW.Text)
                            s:AttemptSave()
                        end
                    )
                else
                    bW:GetPropertyChangedSignal("Text"):Connect(
                        function()
                            bS:SetValue(bW.Text)
                            s:AttemptSave()
                        end
                    )
                end
                local function bX()
                    local bY = 2
                    local bZ = bb["AbsoluteSize"]["X"]
                    if (not bW:IsFocused() or (bW["TextBounds"]["X"] <= (bZ - (2 * bY)))) then
                        bW["Position"] = UDim2.new(0, bY, 0, 0)
                    else
                        local b_ = bW["CursorPosition"]
                        if ((b_ ~= -1) or (4169 == 2187)) then
                            local c0 = string.sub(bW.Text, 1, b_ - 1)
                            local c1 = h:GetTextSize(c0, bW.TextSize, bW.Font, Vector2.new(math.huge, math.huge))["X"]
                            local c2 = bW["Position"]["X"]["Offset"] + c1
                            if (c2 < bY) then
                                bW["Position"] = UDim2.fromOffset(bY - c1, 0)
                            elseif ((1406 == 1406) and (c2 > ((bZ - bY) - 1))) then
                                bW["Position"] = UDim2.fromOffset(((bZ - c1) - bY) - 1, 0)
                            end
                        end
                    end
                end
                task.spawn(bX)
                bW:GetPropertyChangedSignal("Text"):Connect(bX)
                bW:GetPropertyChangedSignal("CursorPosition"):Connect(bX)
                bW["FocusLost"]:Connect(bX)
                bW["Focused"]:Connect(bX)
                s:AddToRegistry(bW, {TextColor3 = "FontColor"})
                bS.OnChanged = function(self, a_)
                    bS["Changed"] = a_
                    a_(bS.Value)
                end
                bw:AddBlank(5)
                bw:Resize()
                Options[af] = bS
                return bS
            end
            am.AddToggle = function(self, af, an)
                assert(an.Text, "AddInput: Missing `Text` string.")
                local c3 = {
                    Value = (an["Default"] or false),
                    Type = "Toggle",
                    Callback = (an["Callback"] or function(I)
                        end),
                    Addons = {},
                    Risky = an["Risky"]
                }
                local bw = self
                local bb = bw["Container"]
                local c4 =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(0, 13, 0, 13),
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                s:AddToRegistry(c4, {BorderColor3 = "Black"})
                local c5 =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 6,
                        Parent = c4
                    }
                )
                s:AddToRegistry(c5, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                local ao =
                    s:CreateLabel(
                    {
                        Size = UDim2.new(0, 216, 1, 0),
                        Position = UDim2.new(1, 6, 0, 0),
                        TextSize = 14,
                        Text = an["Text"],
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        ZIndex = 6,
                        Parent = c5
                    }
                )
                s:Create(
                    "UIListLayout",
                    {
                        Padding = UDim.new(0, 4),
                        FillDirection = Enum["FillDirection"]["Horizontal"],
                        HorizontalAlignment = Enum["HorizontalAlignment"]["Right"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        Parent = ao
                    }
                )
                local c6 =
                    s:Create(
                    "Frame",
                    {BackgroundTransparency = 1, Size = UDim2.new(0, 80, 1, 0), ZIndex = 8, Parent = c4}
                )
                s:OnHighlight(c6, c4, {BorderColor3 = "AccentColor"}, {BorderColor3 = "Black"})
                c3.UpdateColors = function(self)
                    c3:Display()
                end
                if (type(an.Tooltip) ~= "string") then
                else
                    s:AddToolTip(an.Tooltip, c6)
                end
                c3.Display = function(self)
                    c5["BackgroundColor3"] = (c3["Value"] and s["AccentColor"]) or s["MainColor"]
                    c5["BorderColor3"] = (c3["Value"] and s["AccentColorDark"]) or s["OutlineColor"]
                    s["RegistryMap"][c5]["Properties"]["BackgroundColor3"] =
                        (c3["Value"] and "AccentColor") or "MainColor"
                    s["RegistryMap"][c5]["Properties"]["BorderColor3"] =
                        (c3["Value"] and "AccentColorDark") or "OutlineColor"
                end
                c3.OnChanged = function(self, a_)
                    c3["Changed"] = a_
                    a_(c3.Value)
                end
                c3.SetValue = function(self, c7)
                    c7 = not (not c7)
                    c3["Value"] = c7
                    c3:Display()
                    for D, c8 in next, c3["Addons"] do
                        if ((c8["Type"] == "KeyPicker") and c8["SyncToggleState"]) then
                            c8["Toggled"] = c7
                            c8:Update()
                        end
                    end
                    s:SafeCallback(c3.Callback, c3.Value)
                    s:SafeCallback(c3.Changed, c3.Value)
                    s:UpdateDependencyBoxes()
                end
                c6["InputBegan"]:Connect(
                    function(M)
                        if
                            ((1531 < 4271) and (M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            c3:SetValue(not c3["Value"])
                            s:AttemptSave()
                        end
                    end
                )
                if c3["Risky"] then
                    s:RemoveFromRegistry(ao)
                    ao["TextColor3"] = s["RiskColor"]
                    s:AddToRegistry(ao, {TextColor3 = "RiskColor"})
                end
                c3:Display()
                bw:AddBlank(an["BlankSize"] or (5 + 2))
                bw:Resize()
                c3["TextLabel"] = ao
                c3["Container"] = bb
                setmetatable(c3, al)
                Toggles[af] = c3
                s:UpdateDependencyBoxes()
                return c3
            end
            am.AddSlider = function(self, af, an)
                assert(an.Default, "AddSlider: Missing default value.")
                assert(an.Text, "AddSlider: Missing slider text.")
                assert(an.Min, "AddSlider: Missing minimum value.")
                assert(an.Max, "AddSlider: Missing maximum value.")
                assert(an.Rounding, "AddSlider: Missing rounding value.")
                local c9 = {
                    Value = an["Default"],
                    Min = an["Min"],
                    Max = an["Max"],
                    Rounding = an["Rounding"],
                    MaxSize = 232,
                    Type = "Slider",
                    Callback = (an["Callback"] or function(I)
                        end)
                }
                local bw = self
                local bb = bw["Container"]
                if not an["Compact"] then
                    s:CreateLabel(
                        {
                            Size = UDim2.new(1, 0, 0, 10),
                            TextSize = 14,
                            Text = an["Text"],
                            TextXAlignment = Enum["TextXAlignment"]["Left"],
                            TextYAlignment = Enum["TextYAlignment"]["Bottom"],
                            ZIndex = 5,
                            Parent = bb
                        }
                    )
                    bw:AddBlank(3)
                end
                local ca =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(1, -4, 0, 13),
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                s:AddToRegistry(ca, {BorderColor3 = "Black"})
                local cb =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 6,
                        Parent = ca
                    }
                )
                s:AddToRegistry(cb, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                local cc =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["AccentColor"],
                        BorderColor3 = s["AccentColorDark"],
                        Size = UDim2.new(0, 0, 1, 0),
                        ZIndex = 7,
                        Parent = cb
                    }
                )
                s:AddToRegistry(cc, {BackgroundColor3 = "AccentColor", BorderColor3 = "AccentColorDark"})
                local cd =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["AccentColor"],
                        BorderSizePixel = 0,
                        Position = UDim2.new(1, 0, 0, 0),
                        Size = UDim2.new(0, 1, 1, 0),
                        ZIndex = 8,
                        Parent = cc
                    }
                )
                s:AddToRegistry(cd, {BackgroundColor3 = "AccentColor"})
                local aL =
                    s:CreateLabel(
                    {Size = UDim2.new(1, 0, 1, 0), TextSize = 14, Text = "Infinite", ZIndex = 9, Parent = cb}
                )
                s:OnHighlight(ca, ca, {BorderColor3 = "AccentColor"}, {BorderColor3 = "Black"})
                if ((635 == 635) and (type(an.Tooltip) == "string")) then
                    s:AddToolTip(an.Tooltip, ca)
                end
                c9.UpdateColors = function(self)
                    cc["BackgroundColor3"] = s["AccentColor"]
                    cc["BorderColor3"] = s["AccentColorDark"]
                end
                c9.Display = function(self)
                    local ce = an["Suffix"] or ""
                    if ((3373 <= 3556) and an["Compact"]) then
                        aL["Text"] = an["Text"] .. ": " .. c9["Value"] .. ce
                    elseif (an["HideMax"] or (3291 < 3280)) then
                        aL["Text"] = string.format("%s", c9["Value"] .. ce)
                    else
                        aL["Text"] = string.format("%s/%s", c9["Value"] .. ce, c9["Max"] .. ce)
                    end
                    local Q = math.ceil(s:MapValue(c9.Value, c9.Min, c9.Max, 0, c9.MaxSize))
                    cc["Size"] = UDim2.new(0, Q, 1, 0)
                    cd["Visible"] = not ((Q == c9["MaxSize"]) or (Q == 0))
                end
                c9.OnChanged = function(self, a_)
                    c9["Changed"] = a_
                    a_(c9.Value)
                end
                local function cf(I)
                    if (c9["Rounding"] ~= 0) then
                    else
                        return math.floor(I)
                    end
                    return tonumber(string.format("%." .. c9["Rounding"] .. "f", I))
                end
                c9.GetValueFromXOffset = function(self, Q)
                    return cf(s:MapValue(Q, 0, c9.MaxSize, c9.Min, c9.Max))
                end
                c9.SetValue = function(self, aR)
                    local cg = tonumber(aR)
                    if ((4386 >= 873) and not cg) then
                        return
                    end
                    cg = math.clamp(cg, c9.Min, c9.Max)
                    c9["Value"] = cg
                    c9:Display()
                    s:SafeCallback(c9.Callback, c9.Value)
                    s:SafeCallback(c9.Changed, c9.Value)
                end
                cb["InputBegan"]:Connect(
                    function(M)
                        if
                            ((921 <= 1102) and (M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                not s:MouseIsOverOpenedFrame())
                         then
                            local ch = p["X"]
                            local ci = cc["Size"]["X"]["Offset"]
                            local cj = ch - (cc["AbsolutePosition"]["X"] + ci)
                            while g:IsMouseButtonPressed(Enum["UserInputType"].MouseButton1) do
                                local ck = p["X"]
                                local cl = math.clamp(((ci + ck) - ch) + cj, 0, c9.MaxSize)
                                local cm = c9:GetValueFromXOffset(cl)
                                local cn = c9["Value"]
                                c9["Value"] = cm
                                c9:Display()
                                if (cm == cn) then
                                else
                                    s:SafeCallback(c9.Callback, c9.Value)
                                    s:SafeCallback(c9.Changed, c9.Value)
                                end
                                n:Wait()
                            end
                            s:AttemptSave()
                        end
                    end
                )
                c9:Display()
                bw:AddBlank(an["BlankSize"] or 6)
                bw:Resize()
                Options[af] = c9
                return c9
            end
            am.AddDropdown = function(self, af, an)
                if (an["SpecialType"] == "Player") then
                    an["Values"] = u()
                    an["AllowNull"] = true
                elseif ((4706 >= 963) and (an["SpecialType"] == "Team")) then
                    an["Values"] = z()
                    an["AllowNull"] = true
                end
                assert(an.Values, "AddDropdown: Missing dropdown value list.")
                assert(
                    an["AllowNull"] or an["Default"],
                    "AddDropdown: Missing default value. Pass `AllowNull` as true if this was intentional."
                )
                if not an["Text"] then
                    an["Compact"] = true
                end
                local co = {
                    Values = an["Values"],
                    Value = (an["Multi"] and {}),
                    Multi = an["Multi"],
                    Type = "Dropdown",
                    SpecialType = an["SpecialType"],
                    Callback = (an["Callback"] or function(I)
                        end)
                }
                local bw = self
                local bb = bw["Container"]
                local cp = 0
                if not an["Compact"] then
                    local cq =
                        s:CreateLabel(
                        {
                            Size = UDim2.new(1, 0, 0, 10),
                            TextSize = 14,
                            Text = an["Text"],
                            TextXAlignment = Enum["TextXAlignment"]["Left"],
                            TextYAlignment = Enum["TextYAlignment"]["Bottom"],
                            ZIndex = 5,
                            Parent = bb
                        }
                    )
                    bw:AddBlank(3)
                end
                for D, cr in next, bb:GetChildren() do
                    if (not cr:IsA("UIListLayout") or (960 <= 876)) then
                        cp = cp + cr["Size"]["Y"]["Offset"]
                    end
                end
                local cs =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        Size = UDim2.new(1, -4, 0, 20),
                        ZIndex = 5,
                        Parent = bb
                    }
                )
                s:AddToRegistry(cs, {BorderColor3 = "Black"})
                local ct =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 6,
                        Parent = cs
                    }
                )
                s:AddToRegistry(ct, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                s:Create(
                    "UIGradient",
                    {
                        Color = ColorSequence.new(
                            {
                                ColorSequenceKeypoint.new(0, Color3.new(1, 1, 1)),
                                ColorSequenceKeypoint.new(1, Color3.fromRGB(212, 212, 212))
                            }
                        ),
                        Rotation = 90,
                        Parent = ct
                    }
                )
                local cu =
                    s:Create(
                    "ImageLabel",
                    {
                        AnchorPoint = Vector2.new(0, 0.5),
                        BackgroundTransparency = 1,
                        Position = UDim2.new(1, -16, 0.5, 0),
                        Size = UDim2.new(0, 12, 0, 12),
                        Image = "http://www.roblox.com/asset/?id=6282522798",
                        ZIndex = 8,
                        Parent = ct
                    }
                )
                local cv =
                    s:CreateLabel(
                    {
                        Position = UDim2.new(0, 5, 0, 0),
                        Size = UDim2.new(1, -5, 1, 0),
                        TextSize = 14,
                        Text = "--",
                        TextXAlignment = Enum["TextXAlignment"]["Left"],
                        TextWrapped = true,
                        ZIndex = 7,
                        Parent = ct
                    }
                )
                s:OnHighlight(cs, cs, {BorderColor3 = "AccentColor"}, {BorderColor3 = "Black"})
                if ((type(an.Tooltip) == "string") or (2066 == 932)) then
                    s:AddToolTip(an.Tooltip, cs)
                end
                local cw = 8
                local cx =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = Color3.new(0, 0, 0),
                        BorderColor3 = Color3.new(0, 0, 0),
                        ZIndex = 20,
                        Visible = false,
                        Parent = r
                    }
                )
                local function cy()
                    cx["Position"] =
                        UDim2.fromOffset(
                        cs["AbsolutePosition"].X,
                        cs["AbsolutePosition"]["Y"] + cs["Size"]["Y"]["Offset"] + 1
                    )
                end
                local function cz(bo)
                    cx["Size"] = UDim2.fromOffset(cs["AbsoluteSize"].X, bo or ((cw * 20) + 2))
                end
                cy()
                cz()
                cs:GetPropertyChangedSignal("AbsolutePosition"):Connect(cy)
                local cA =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderColor3 = s["OutlineColor"],
                        BorderMode = Enum["BorderMode"]["Inset"],
                        BorderSizePixel = 0,
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 21,
                        Parent = cx
                    }
                )
                s:AddToRegistry(cA, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                local cB =
                    s:Create(
                    "ScrollingFrame",
                    {
                        BackgroundTransparency = 1,
                        BorderSizePixel = 0,
                        CanvasSize = UDim2.new(0, 0, 0, 0),
                        Size = UDim2.new(1, 0, 1, 0),
                        ZIndex = 21,
                        Parent = cA,
                        TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png",
                        BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png",
                        ScrollBarThickness = 3,
                        ScrollBarImageColor3 = s["AccentColor"]
                    }
                )
                s:AddToRegistry(cB, {ScrollBarImageColor3 = "AccentColor"})
                s:Create(
                    "UIListLayout",
                    {
                        Padding = UDim.new(0, 0),
                        FillDirection = Enum["FillDirection"]["Vertical"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        Parent = cB
                    }
                )
                co.Display = function(self)
                    local cC = co["Values"]
                    local aR = ""
                    if an["Multi"] then
                        for af, I in next, cC do
                            if ((4825 < 4843) and co["Value"][I]) then
                                aR = aR .. I .. ", "
                            end
                        end
                        aR = aR:sub(1, #aR - 2)
                    else
                        aR = co["Value"] or ""
                    end
                    cv["Text"] = ((aR == "") and "--") or aR
                end
                co.GetActiveValues = function(self)
                    if (an["Multi"] or (3877 >= 4537)) then
                        local cD = {}
                        for I, c7 in next, co["Value"] do
                            table.insert(cD, I)
                        end
                        return cD
                    else
                        return (co["Value"] and 1) or 0
                    end
                end
                co.BuildDropdownList = function(self)
                    local cC = co["Values"]
                    local cE = {}
                    for D, cr in next, cB:GetChildren() do
                        if (not cr:IsA("UIListLayout") or (4315 < 1726)) then
                            cr:Destroy()
                        end
                    end
                    local cF = 0
                    for af, I in next, cC do
                        local bu = {}
                        cF = cF + 1
                        local aS =
                            s:Create(
                            "Frame",
                            {
                                BackgroundColor3 = s["MainColor"],
                                BorderColor3 = s["OutlineColor"],
                                BorderMode = Enum["BorderMode"]["Middle"],
                                Size = UDim2.new(1, -1, 0, 20),
                                ZIndex = 23,
                                Active = true,
                                Parent = cB
                            }
                        )
                        s:AddToRegistry(aS, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
                        local cG =
                            s:CreateLabel(
                            {
                                Active = false,
                                Size = UDim2.new(1, -6, 1, 0),
                                Position = UDim2.new(0, 6, 0, 0),
                                TextSize = 14,
                                Text = I,
                                TextXAlignment = Enum["TextXAlignment"]["Left"],
                                ZIndex = 25,
                                Parent = aS
                            }
                        )
                        s:OnHighlight(
                            aS,
                            aS,
                            {BorderColor3 = "AccentColor", ZIndex = 24},
                            {BorderColor3 = "OutlineColor", ZIndex = 23}
                        )
                        local cH
                        if (an["Multi"] or (3679 < 625)) then
                            cH = co["Value"][I]
                        else
                            cH = co["Value"] == I
                        end
                        bu.UpdateButton = function(self)
                            if (an["Multi"] or (4625 < 632)) then
                                cH = co["Value"][I]
                            else
                                cH = co["Value"] == I
                            end
                            cG["TextColor3"] = (cH and s["AccentColor"]) or s["FontColor"]
                            s["RegistryMap"][cG]["Properties"]["TextColor3"] = (cH and "AccentColor") or "FontColor"
                        end
                        cG["InputBegan"]:Connect(
                            function(M)
                                if ((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) or (83 > 1780)) then
                                    local cI = not cH
                                    if
                                        ((546 <= 1077) and (co:GetActiveValues() == 1) and not cI and
                                            not an["AllowNull"])
                                     then
                                    else
                                        if an["Multi"] then
                                            cH = cI
                                            if cH then
                                                co["Value"][I] = true
                                            else
                                                co["Value"][I] = nil
                                            end
                                        else
                                            cH = cI
                                            if (cH or (996 > 4301)) then
                                                co["Value"] = I
                                            else
                                                co["Value"] = nil
                                            end
                                            for D, cJ in next, cE do
                                                cJ:UpdateButton()
                                            end
                                        end
                                        bu:UpdateButton()
                                        co:Display()
                                        s:SafeCallback(co.Callback, co.Value)
                                        s:SafeCallback(co.Changed, co.Value)
                                        s:UpdateDependencyBoxes()
                                        s:AttemptSave()
                                    end
                                end
                            end
                        )
                        bu:UpdateButton()
                        co:Display()
                        cE[aS] = bu
                    end
                    cB["CanvasSize"] = UDim2.fromOffset(0, (cF * 20) + 1)
                    local R = math.clamp(cF * 20, 0, cw * 20) + 1
                    cz(R)
                end
                co.SetValues = function(self, cK)
                    if cK then
                        co["Values"] = cK
                    end
                    co:BuildDropdownList()
                end
                co.OpenDropdown = function(self)
                    cx["Visible"] = true
                    s["OpenedFrames"][cx] = true
                    cu["Rotation"] = 180
                end
                co.CloseDropdown = function(self)
                    cx["Visible"] = false
                    s["OpenedFrames"][cx] = nil
                    cu["Rotation"] = 0
                end
                co.OnChanged = function(self, a_)
                    co["Changed"] = a_
                    a_(co.Value)
                end
                co.SetValue = function(self, b0)
                    if co["Multi"] then
                        local cL = {}
                        for I, c7 in next, b0 do
                            if table.find(co.Values, I) then
                                cL[I] = true
                            end
                        end
                        co["Value"] = cL
                    elseif not b0 then
                        co["Value"] = nil
                    elseif ((4070 > 687) and table.find(co.Values, b0)) then
                        co["Value"] = b0
                    end
                    co:BuildDropdownList()
                    s:SafeCallback(co.Callback, co.Value)
                    s:SafeCallback(co.Changed, co.Value)
                end
                cs["InputBegan"]:Connect(
                    function(M)
                        if
                            (((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                not s:MouseIsOverOpenedFrame()) or
                                (656 >= 3330))
                         then
                            if cx["Visible"] then
                                co:CloseDropdown()
                            else
                                co:OpenDropdown()
                            end
                        end
                    end
                )
                g["InputBegan"]:Connect(
                    function(M, b9)
                        if (b9 or g:GetFocusedTextBox() or (2492 <= 335)) then
                            return
                        end
                        if (M["UserInputType"] ~= Enum["UserInputType"]["MouseButton1"]) then
                        else
                            local _, a0 = cx["AbsolutePosition"], cx["AbsoluteSize"]
                            if
                                ((p["X"] < _["X"]) or (p["X"] > (_["X"] + a0["X"])) or (p["Y"] < ((_["Y"] - 20) - 1)) or
                                    (p["Y"] > (_["Y"] + a0["Y"])))
                             then
                                co:CloseDropdown()
                            end
                        end
                    end
                )
                co:BuildDropdownList()
                co:Display()
                local cM = {}
                if ((4322 >= 2562) and (type(an.Default) == "string")) then
                    local af = table.find(co.Values, an.Default)
                    if af then
                        table.insert(cM, af)
                    end
                elseif ((type(an.Default) == "table") or (3637 >= 3770)) then
                    for D, I in next, an["Default"] do
                        local af = table.find(co.Values, I)
                        if af then
                            table.insert(cM, af)
                        end
                    end
                elseif ((type(an.Default) == "number") and (co["Values"][an["Default"]] ~= nil)) then
                    table.insert(cM, an.Default)
                end
                if next(cM) then
                    for w = 1, #cM do
                        local cN = cM[w]
                        if (an["Multi"] or (2379 > 4578)) then
                            co["Value"][co["Values"][cN]] = true
                        else
                            co["Value"] = co["Values"][cN]
                        end
                        if not an["Multi"] then
                            break
                        end
                    end
                    co:BuildDropdownList()
                    co:Display()
                end
                bw:AddBlank(an["BlankSize"] or 5)
                bw:Resize()
                Options[af] = co
                return co
            end
            am.AddDependencyBox = function(self)
                local a1 = {Dependencies = {}}
                local bw = self
                local bb = bw["Container"]
                local cO =
                    s:Create(
                    "Frame",
                    {BackgroundTransparency = 1, Size = UDim2.new(1, 0, 0, 0), Visible = false, Parent = bb}
                )
                local Z =
                    s:Create(
                    "Frame",
                    {BackgroundTransparency = 1, Size = UDim2.new(1, 0, 1, 0), Visible = true, Parent = cO}
                )
                local cP =
                    s:Create(
                    "UIListLayout",
                    {
                        FillDirection = Enum["FillDirection"]["Vertical"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        Parent = Z
                    }
                )
                a1.Resize = function(self)
                    cO["Size"] = UDim2.new(1, 0, 0, cP["AbsoluteContentSize"].Y)
                    bw:Resize()
                end
                cP:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(
                    function()
                        a1:Resize()
                    end
                )
                cO:GetPropertyChangedSignal("Visible"):Connect(
                    function()
                        a1:Resize()
                    end
                )
                a1.Update = function(self)
                    for D, cQ in next, a1["Dependencies"] do
                        local cR = cQ[1]
                        local I = cQ[2]
                        if ((cR["Type"] == "Toggle") and (cR["Value"] ~= I)) then
                            cO["Visible"] = false
                            a1:Resize()
                            return
                        end
                        if ((cR["Type"] == "Dropdown") and not cR["Multi"]) then
                            if (cR["Value"] == I) then
                            else
                                cO["Visible"] = false
                                a1:Resize()
                                return
                            end
                        end
                        if (((cR["Type"] == "Dropdown") and cR["Multi"]) or (483 > 743)) then
                            if ((2454 > 578) and (type(I) == "string")) then
                                if not cR["Value"][I] then
                                    cO["Visible"] = false
                                    a1:Resize()
                                    return
                                end
                            end
                        end
                    end
                    cO["Visible"] = true
                    a1:Resize()
                end
                a1.SetupDependencies = function(self, cS)
                    for D, cQ in next, cS do
                        assert(type(cQ) == "table", "SetupDependencies: Dependency is not of type `table`.")
                        assert(cQ[1], "SetupDependencies: Dependency is missing element argument.")
                        assert(cQ[2] ~= nil, "SetupDependencies: Dependency is missing value argument.")
                    end
                    a1["Dependencies"] = cS
                    a1:Update()
                end
                a1["Container"] = Z
                setmetatable(a1, bv)
                table.insert(s.DependencyBoxes, a1)
                return a1
            end
            bv["__index"] = am
            bv.__namecall = function(bu, bq, ...)
                return am[bq](...)
            end
        end
        do
            s["NotificationArea"] =
                s:Create(
                "Frame",
                {
                    BackgroundTransparency = 1,
                    Position = UDim2.new(0, 0, 0, 40),
                    Size = UDim2.new(0, 300, 0, 200),
                    ZIndex = 100,
                    Parent = r
                }
            )
            s:Create(
                "UIListLayout",
                {
                    Padding = UDim.new(0, 4),
                    FillDirection = Enum["FillDirection"]["Vertical"],
                    SortOrder = Enum["SortOrder"]["LayoutOrder"],
                    Parent = s["NotificationArea"]
                }
            )
            local cT =
                s:Create(
                "Frame",
                {
                    BorderColor3 = Color3.new(0, 0, 0),
                    Position = UDim2.new(0, 100, 0, -25),
                    Size = UDim2.new(0, 213, 0, 20),
                    ZIndex = 200,
                    Visible = false,
                    Parent = r
                }
            )
            local cU =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["AccentColor"],
                    BorderMode = Enum["BorderMode"]["Inset"],
                    Size = UDim2.new(1, 0, 1, 0),
                    ZIndex = 201,
                    Parent = cT
                }
            )
            s:AddToRegistry(cU, {BorderColor3 = "AccentColor"})
            local cV =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = Color3.new(1, 1, 1),
                    BorderSizePixel = 0,
                    Position = UDim2.new(0, 1, 0, 1),
                    Size = UDim2.new(1, -2, 1, -2),
                    ZIndex = 202,
                    Parent = cU
                }
            )
            local cW =
                s:Create(
                "UIGradient",
                {
                    Color = ColorSequence.new(
                        {
                            ColorSequenceKeypoint.new(0, s:GetDarkerColor(s.MainColor)),
                            ColorSequenceKeypoint.new(1, s.MainColor)
                        }
                    ),
                    Rotation = -90,
                    Parent = cV
                }
            )
            s:AddToRegistry(
                cW,
                {
                    Color = function()
                        return ColorSequence.new(
                            {
                                ColorSequenceKeypoint.new(0, s:GetDarkerColor(s.MainColor)),
                                ColorSequenceKeypoint.new(1, s.MainColor)
                            }
                        )
                    end
                }
            )
            local cX =
                s:CreateLabel(
                {
                    Position = UDim2.new(0, 5, 0, 0),
                    Size = UDim2.new(1, -4, 1, 0),
                    TextSize = 14,
                    TextXAlignment = Enum["TextXAlignment"]["Left"],
                    ZIndex = 203,
                    Parent = cV
                }
            )
            s["Watermark"] = cT
            s["WatermarkText"] = cX
            s:MakeDraggable(s.Watermark)
            local cY =
                s:Create(
                "Frame",
                {
                    AnchorPoint = Vector2.new(0, 0.5),
                    BorderColor3 = Color3.new(0, 0, 0),
                    Position = UDim2.new(0, 10, 0.5, 0),
                    Size = UDim2.new(0, 210, 0, 20),
                    Visible = false,
                    ZIndex = 100,
                    Parent = r
                }
            )
            local cZ =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["OutlineColor"],
                    BorderMode = Enum["BorderMode"]["Inset"],
                    Size = UDim2.new(1, 0, 1, 0),
                    ZIndex = 101,
                    Parent = cY
                }
            )
            s:AddToRegistry(cZ, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"}, true)
            local c_ =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["AccentColor"],
                    BorderSizePixel = 0,
                    Size = UDim2.new(1, 0, 0, 2),
                    ZIndex = 102,
                    Parent = cZ
                }
            )
            s:AddToRegistry(c_, {BackgroundColor3 = "AccentColor"}, true)
            local d0 =
                s:CreateLabel(
                {
                    Size = UDim2.new(1, 0, 0, 20),
                    Position = UDim2.fromOffset(5, 2),
                    TextXAlignment = Enum["TextXAlignment"]["Left"],
                    Text = "Keybinds",
                    ZIndex = 104,
                    Parent = cZ
                }
            )
            local d1 =
                s:Create(
                "Frame",
                {
                    BackgroundTransparency = 1,
                    Size = UDim2.new(1, 0, 1, -20),
                    Position = UDim2.new(0, 0, 0, 20),
                    ZIndex = 1,
                    Parent = cZ
                }
            )
            s:Create(
                "UIListLayout",
                {
                    FillDirection = Enum["FillDirection"]["Vertical"],
                    SortOrder = Enum["SortOrder"]["LayoutOrder"],
                    Parent = d1
                }
            )
            s:Create("UIPadding", {PaddingLeft = UDim.new(0, 5), Parent = d1})
            s["KeybindFrame"] = cY
            s["KeybindContainer"] = d1
            s:MakeDraggable(cY)
        end
        s.SetWatermarkVisibility = function(self, c7)
            s["Watermark"]["Visible"] = c7
        end
        s.SetWatermark = function(self, a6)
            local Q, R = s:GetTextBounds(a6, s.Font, 14)
            s["Watermark"]["Size"] = UDim2.new(0, Q + 15, 0, (R * 1.5) + 3)
            s:SetWatermarkVisibility(true)
            s["WatermarkText"]["Text"] = a6
        end
        s.Notify = function(self, a6, d2)
            local bp, bo = s:GetTextBounds(a6, s.Font, 14)
            bo = bo + 7
            local d3 =
                s:Create(
                "Frame",
                {
                    BorderColor3 = Color3.new(0, 0, 0),
                    Position = UDim2.new(0, 100, 0, 10),
                    Size = UDim2.new(0, 0, 0, bo),
                    ClipsDescendants = true,
                    ZIndex = 100,
                    Parent = s["NotificationArea"]
                }
            )
            local d4 =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["OutlineColor"],
                    BorderMode = Enum["BorderMode"]["Inset"],
                    Size = UDim2.new(1, 0, 1, 0),
                    ZIndex = 101,
                    Parent = d3
                }
            )
            s:AddToRegistry(d4, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"}, true)
            local cV =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = Color3.new(1, 1, 1),
                    BorderSizePixel = 0,
                    Position = UDim2.new(0, 1, 0, 1),
                    Size = UDim2.new(1, -2, 1, -2),
                    ZIndex = 102,
                    Parent = d4
                }
            )
            local cW =
                s:Create(
                "UIGradient",
                {
                    Color = ColorSequence.new(
                        {
                            ColorSequenceKeypoint.new(0, s:GetDarkerColor(s.MainColor)),
                            ColorSequenceKeypoint.new(1, s.MainColor)
                        }
                    ),
                    Rotation = -90,
                    Parent = cV
                }
            )
            s:AddToRegistry(
                cW,
                {
                    Color = function()
                        return ColorSequence.new(
                            {
                                ColorSequenceKeypoint.new(0, s:GetDarkerColor(s.MainColor)),
                                ColorSequenceKeypoint.new(1, s.MainColor)
                            }
                        )
                    end
                }
            )
            local d5 =
                s:CreateLabel(
                {
                    Position = UDim2.new(0, 4, 0, 0),
                    Size = UDim2.new(1, -4, 1, 0),
                    Text = a6,
                    TextXAlignment = Enum["TextXAlignment"]["Left"],
                    TextSize = 14,
                    ZIndex = 103,
                    Parent = cV
                }
            )
            local d6 =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["AccentColor"],
                    BorderSizePixel = 0,
                    Position = UDim2.new(0, -1, 0, -1),
                    Size = UDim2.new(0, 3, 1, 2),
                    ZIndex = 104,
                    Parent = d3
                }
            )
            s:AddToRegistry(d6, {BackgroundColor3 = "AccentColor"}, true)
            pcall(d3.TweenSize, d3, UDim2.new(0, bp + 8 + 4, 0, bo), "Out", "Quad", 0.4, true)
            task.spawn(
                function()
                    wait(d2 or 5)
                    pcall(d3.TweenSize, d3, UDim2.new(0, 0, 0, bo), "Out", "Quad", 0.4, true)
                    wait(0.4)
                    d3:Destroy()
                end
            )
        end
        s.CreateWindow = function(self, ...)
            local d7 = {...}
            local d8 = {AnchorPoint = Vector2["zero"]}
            if (type(...) == "table") then
                d8 = ...
            else
                d8["Title"] = d7[1]
                d8["AutoShow"] = d7[2] or false
            end
            if (type(d8.Title) == "string") then
            else
                d8["Title"] = "No title"
            end
            if (type(d8.TabPadding) ~= "number") then
                d8["TabPadding"] = 0
            end
            if (type(d8.MenuFadeTime) ~= "number") then
                d8["MenuFadeTime"] = 0.2
            end
            if (typeof(d8.Position) == "UDim2") then
            else
                d8["Position"] = UDim2.fromOffset(175, 50)
            end
            if ((930 < 4458) and (typeof(d8.Size) ~= "UDim2")) then
                d8["Size"] = UDim2.fromOffset(550, 600)
            end
            if ((662 <= 972) and d8["Center"]) then
                d8["AnchorPoint"] = Vector2.new(0.5, 0.5)
                d8["Position"] = UDim2.fromScale(0.5, 0.5)
            end
            local d9 = {Tabs = {}}
            local bD =
                s:Create(
                "Frame",
                {
                    AnchorPoint = d8["AnchorPoint"],
                    BackgroundColor3 = Color3.new(0, 0, 0),
                    BorderSizePixel = 0,
                    Position = d8["Position"],
                    Size = d8["Size"],
                    Visible = false,
                    ZIndex = 1,
                    Parent = r
                }
            )
            s:MakeDraggable(bD, 25)
            local bE =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["AccentColor"],
                    BorderMode = Enum["BorderMode"]["Inset"],
                    Position = UDim2.new(0, 1, 0, 1),
                    Size = UDim2.new(1, -2, 1, -2),
                    ZIndex = 1,
                    Parent = bD
                }
            )
            s:AddToRegistry(bE, {BackgroundColor3 = "MainColor", BorderColor3 = "AccentColor"})
            local da =
                s:CreateLabel(
                {
                    Position = UDim2.new(0, 7, 0, 0),
                    Size = UDim2.new(0, 0, 0, 25),
                    Text = (d8["Title"] or ""),
                    TextXAlignment = Enum["TextXAlignment"]["Left"],
                    ZIndex = 1,
                    Parent = bE
                }
            )
local db = s:Create("Frame", {
    BackgroundColor3 = s.MainColor or Color3.fromRGB(30, 30, 30),
    BorderColor3 = s.OutlineColor or Color3.fromRGB(60, 60, 60),
    Position = UDim2.new(0, 8, 0, 25),
    Size = UDim2.new(1, -16, 1, -33),
    ZIndex = 1,
    Parent = bE
})


            s:AddToRegistry(db, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
            local dc =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["BackgroundColor"],
                    BorderColor3 = Color3.new(0, 0, 0),
                    BorderMode = Enum["BorderMode"]["Inset"],
                    Position = UDim2.new(0, 0, 0, 0),
                    Size = UDim2.new(1, 0, 1, 0),
                    ZIndex = 1,
                    Parent = db
                }
            )
            s:AddToRegistry(dc, {BackgroundColor3 = "BackgroundColor"})
            local dd =
                s:Create(
                "Frame",
                {
                    BackgroundTransparency = 1,
                    Position = UDim2.new(0, 8, 0, 8),
                    Size = UDim2.new(1, -16, 0, 21),
                    ZIndex = 1,
                    Parent = dc
                }
            )
            local de =
                s:Create(
                "UIListLayout",
                {
                    Padding = UDim.new(0, d8.TabPadding),
                    FillDirection = Enum["FillDirection"]["Horizontal"],
                    SortOrder = Enum["SortOrder"]["LayoutOrder"],
                    Parent = dd
                }
            )
            local df =
                s:Create(
                "Frame",
                {
                    BackgroundColor3 = s["MainColor"],
                    BorderColor3 = s["OutlineColor"],
                    Position = UDim2.new(0, 8, 0, 30),
                    Size = UDim2.new(1, -16, 1, -38),
                    ZIndex = 2,
                    Parent = dc
                }
            )
            s:AddToRegistry(df, {BackgroundColor3 = "MainColor", BorderColor3 = "OutlineColor"})
            d9.SetWindowTitle = function(self, dg)
                da["Text"] = dg
            end
            d9.AddTab = function(self, dh)
                local di = {Groupboxes = {}, Tabboxes = {}}
                local dj = s:GetTextBounds(dh, s.Font, 16)
                local dk =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["BackgroundColor"],
                        BorderColor3 = s["OutlineColor"],
                        Size = UDim2.new(0, dj + 8 + 4, 1, 0),
                        ZIndex = 1,
                        Parent = dd
                    }
                )
                s:AddToRegistry(dk, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                local dl =
                    s:CreateLabel(
                    {
                        Position = UDim2.new(0, 0, 0, 0),
                        Size = UDim2.new(1, 0, 1, -1),
                        Text = dh,
                        ZIndex = 1,
                        Parent = dk
                    }
                )
                local dm =
                    s:Create(
                    "Frame",
                    {
                        BackgroundColor3 = s["MainColor"],
                        BorderSizePixel = 0,
                        Position = UDim2.new(0, 0, 1, 0),
                        Size = UDim2.new(1, 0, 0, 1),
                        BackgroundTransparency = 1,
                        ZIndex = 3,
                        Parent = dk
                    }
                )
                s:AddToRegistry(dm, {BackgroundColor3 = "MainColor"})
                local dn =
                    s:Create(
                    "Frame",
                    {
                        Name = "TabFrame",
                        BackgroundTransparency = 1,
                        Position = UDim2.new(0, 0, 0, 0),
                        Size = UDim2.new(1, 0, 1, 0),
                        Visible = false,
                        ZIndex = 2,
                        Parent = df
                    }
                )
                local dp =
                    s:Create(
                    "ScrollingFrame",
                    {
                        BackgroundTransparency = 1,
                        BorderSizePixel = 0,
                        Position = UDim2.new(0, 8 - 1, 0, 8 - 1),
                        Size = UDim2.new(0.5, -12 + 2, 0, 507 + 2),
                        CanvasSize = UDim2.new(0, 0, 0, 0),
                        BottomImage = "",
                        TopImage = "",
                        ScrollBarThickness = 0,
                        ZIndex = 2,
                        Parent = dn
                    }
                )
                local dq =
                    s:Create(
                    "ScrollingFrame",
                    {
                        BackgroundTransparency = 1,
                        BorderSizePixel = 0,
                        Position = UDim2.new(0.5, 4 + 1, 0, 8 - 1),
                        Size = UDim2.new(0.5, -12 + 2, 0, 507 + 2),
                        CanvasSize = UDim2.new(0, 0, 0, 0),
                        BottomImage = "",
                        TopImage = "",
                        ScrollBarThickness = 0,
                        ZIndex = 2,
                        Parent = dn
                    }
                )
                s:Create(
                    "UIListLayout",
                    {
                        Padding = UDim.new(0, 8),
                        FillDirection = Enum["FillDirection"]["Vertical"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        HorizontalAlignment = Enum["HorizontalAlignment"]["Center"],
                        Parent = dp
                    }
                )
                s:Create(
                    "UIListLayout",
                    {
                        Padding = UDim.new(0, 8),
                        FillDirection = Enum["FillDirection"]["Vertical"],
                        SortOrder = Enum["SortOrder"]["LayoutOrder"],
                        HorizontalAlignment = Enum["HorizontalAlignment"]["Center"],
                        Parent = dq
                    }
                )
                for D, dr in next, {dp, dq} do
                    dr:WaitForChild("UIListLayout"):GetPropertyChangedSignal("AbsoluteContentSize"):Connect(
                        function()
                            dr["CanvasSize"] = UDim2.fromOffset(0, dr["UIListLayout"]["AbsoluteContentSize"].Y)
                        end
                    )
                end
                di.ShowTab = function(self)
                    for D, di in next, d9["Tabs"] do
                        di:HideTab()
                    end
                    dm["BackgroundTransparency"] = 0
                    dk["BackgroundColor3"] = s["MainColor"]
                    s["RegistryMap"][dk]["Properties"]["BackgroundColor3"] = "MainColor"
                    dn["Visible"] = true
                end
                di.HideTab = function(self)
                    dm["BackgroundTransparency"] = 1
                    dk["BackgroundColor3"] = s["BackgroundColor"]
                    s["RegistryMap"][dk]["Properties"]["BackgroundColor3"] = "BackgroundColor"
                    dn["Visible"] = false
                end
                di.SetLayoutOrder = function(self, ds)
                    dk["LayoutOrder"] = ds
                    de:ApplyLayout()
                end
                di.AddGroupbox = function(self, an)
                    local bw = {}
                    local dt =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["BackgroundColor"],
                            BorderColor3 = s["OutlineColor"],
                            BorderMode = Enum["BorderMode"]["Inset"],
                            Size = UDim2.new(1, 0, 0, 507 + 2),
                            ZIndex = 2,
                            Parent = (((an["Side"] == 1) and dp) or dq)
                        }
                    )
                    s:AddToRegistry(dt, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                    local du =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["BackgroundColor"],
                            BorderColor3 = Color3.new(0, 0, 0),
                            Size = UDim2.new(1, -2, 1, -2),
                            Position = UDim2.new(0, 1, 0, 1),
                            ZIndex = 4,
                            Parent = dt
                        }
                    )
                    s:AddToRegistry(du, {BackgroundColor3 = "BackgroundColor"})
                    local au =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["AccentColor"],
                            BorderSizePixel = 0,
                            Size = UDim2.new(1, 0, 0, 2),
                            ZIndex = 5,
                            Parent = du
                        }
                    )
                    s:AddToRegistry(au, {BackgroundColor3 = "AccentColor"})
                    local dv =
                        s:CreateLabel(
                        {
                            Size = UDim2.new(1, 0, 0, 18),
                            Position = UDim2.new(0, 4, 0, 2),
                            TextSize = 14,
                            Text = an["Name"],
                            TextXAlignment = Enum["TextXAlignment"]["Left"],
                            ZIndex = 5,
                            Parent = du
                        }
                    )
                    local bb =
                        s:Create(
                        "Frame",
                        {
                            BackgroundTransparency = 1,
                            Position = UDim2.new(0, 4, 0, 20),
                            Size = UDim2.new(1, -4, 1, -20),
                            ZIndex = 1,
                            Parent = du
                        }
                    )
                    s:Create(
                        "UIListLayout",
                        {
                            FillDirection = Enum["FillDirection"]["Vertical"],
                            SortOrder = Enum["SortOrder"]["LayoutOrder"],
                            Parent = bb
                        }
                    )
                    bw.Resize = function(self)
                        local a8 = 0
                        for D, cr in next, bw["Container"]:GetChildren() do
                            if ((4370 == 4370) and not cr:IsA("UIListLayout") and cr["Visible"]) then
                                a8 = a8 + cr["Size"]["Y"]["Offset"]
                            end
                        end
                        dt["Size"] = UDim2.new(1, 0, 0, 20 + a8 + 2 + 2)
                    end
                    bw["Container"] = bb
                    setmetatable(bw, bv)
                    bw:AddBlank(3)
                    bw:Resize()
                    di["Groupboxes"][an["Name"]] = bw
                    return bw
                end
                di.AddLeftGroupbox = function(self, dh)
                    return di:AddGroupbox({Side = 1, Name = dh})
                end
                di.AddRightGroupbox = function(self, dh)
                    return di:AddGroupbox({Side = 2, Name = dh})
                end
                di.AddTabbox = function(self, an)
                    local dw = {Tabs = {}}
                    local dt =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["BackgroundColor"],
                            BorderColor3 = s["OutlineColor"],
                            BorderMode = Enum["BorderMode"]["Inset"],
                            Size = UDim2.new(1, 0, 0, 0),
                            ZIndex = 2,
                            Parent = (((an["Side"] == 1) and dp) or dq)
                        }
                    )
                    s:AddToRegistry(dt, {BackgroundColor3 = "BackgroundColor", BorderColor3 = "OutlineColor"})
                    local du =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["BackgroundColor"],
                            BorderColor3 = Color3.new(0, 0, 0),
                            Size = UDim2.new(1, -2, 1, -2),
                            Position = UDim2.new(0, 1, 0, 1),
                            ZIndex = 4,
                            Parent = dt
                        }
                    )
                    s:AddToRegistry(du, {BackgroundColor3 = "BackgroundColor"})
                    local au =
                        s:Create(
                        "Frame",
                        {
                            BackgroundColor3 = s["AccentColor"],
                            BorderSizePixel = 0,
                            Size = UDim2.new(1, 0, 0, 2),
                            ZIndex = 10,
                            Parent = du
                        }
                    )
                    s:AddToRegistry(au, {BackgroundColor3 = "AccentColor"})
                    local dx =
                        s:Create(
                        "Frame",
                        {
                            BackgroundTransparency = 1,
                            Position = UDim2.new(0, 0, 0, 1),
                            Size = UDim2.new(1, 0, 0, 18),
                            ZIndex = 5,
                            Parent = du
                        }
                    )
                    s:Create(
                        "UIListLayout",
                        {
                            FillDirection = Enum["FillDirection"]["Horizontal"],
                            HorizontalAlignment = Enum["HorizontalAlignment"]["Left"],
                            SortOrder = Enum["SortOrder"]["LayoutOrder"],
                            Parent = dx
                        }
                    )
                    dw.AddTab = function(self, dh)
                        local di = {}
                        local aS =
                            s:Create(
                            "Frame",
                            {
                                BackgroundColor3 = s["MainColor"],
                                BorderColor3 = Color3.new(0, 0, 0),
                                Size = UDim2.new(0.5, 0, 1, 0),
                                ZIndex = 6,
                                Parent = dx
                            }
                        )
                        s:AddToRegistry(aS, {BackgroundColor3 = "MainColor"})
                        local cG =
                            s:CreateLabel(
                            {
                                Size = UDim2.new(1, 0, 1, 0),
                                TextSize = 14,
                                Text = dh,
                                TextXAlignment = Enum["TextXAlignment"]["Center"],
                                ZIndex = 7,
                                Parent = aS
                            }
                        )
                        local dy =
                            s:Create(
                            "Frame",
                            {
                                BackgroundColor3 = s["BackgroundColor"],
                                BorderSizePixel = 0,
                                Position = UDim2.new(0, 0, 1, 0),
                                Size = UDim2.new(1, 0, 0, 1),
                                Visible = false,
                                ZIndex = 9,
                                Parent = aS
                            }
                        )
                        s:AddToRegistry(dy, {BackgroundColor3 = "BackgroundColor"})
                        local bb =
                            s:Create(
                            "Frame",
                            {
                                BackgroundTransparency = 1,
                                Position = UDim2.new(0, 4, 0, 20),
                                Size = UDim2.new(1, -4, 1, -20),
                                ZIndex = 1,
                                Visible = false,
                                Parent = du
                            }
                        )
                        s:Create(
                            "UIListLayout",
                            {
                                FillDirection = Enum["FillDirection"]["Vertical"],
                                SortOrder = Enum["SortOrder"]["LayoutOrder"],
                                Parent = bb
                            }
                        )
                        di.Show = function(self)
                            for D, di in next, dw["Tabs"] do
                                di:Hide()
                            end
                            bb["Visible"] = true
                            dy["Visible"] = true
                            aS["BackgroundColor3"] = s["BackgroundColor"]
                            s["RegistryMap"][aS]["Properties"]["BackgroundColor3"] = "BackgroundColor"
                            di:Resize()
                        end
                        di.Hide = function(self)
                            bb["Visible"] = false
                            dy["Visible"] = false
                            aS["BackgroundColor3"] = s["MainColor"]
                            s["RegistryMap"][aS]["Properties"]["BackgroundColor3"] = "MainColor"
                        end
                        di.Resize = function(self)
                            local dz = 0
                            for D, di in next, dw["Tabs"] do
                                dz = dz + 1
                            end
                            for D, aS in next, dx:GetChildren() do
                                if (not aS:IsA("UIListLayout") or (4762 <= 861)) then
                                    aS["Size"] = UDim2.new(1 / dz, 0, 1, 0)
                                end
                            end
                            if (not bb["Visible"] or (1412 == 4264)) then
                                return
                            end
                            local a8 = 0
                            for D, cr in next, di["Container"]:GetChildren() do
                                if (not cr:IsA("UIListLayout") and cr["Visible"]) then
                                    a8 = a8 + cr["Size"]["Y"]["Offset"]
                                end
                            end
                            dt["Size"] = UDim2.new(1, 0, 0, 20 + a8 + 2 + 2)
                        end
                        aS["InputBegan"]:Connect(
                            function(M)
                                if
                                    (((M["UserInputType"] == Enum["UserInputType"]["MouseButton1"]) and
                                        not s:MouseIsOverOpenedFrame()) or
                                        (3168 < 2153))
                                 then
                                    di:Show()
                                    di:Resize()
                                end
                            end
                        )
                        di["Container"] = bb
                        dw["Tabs"][dh] = di
                        setmetatable(di, bv)
                        di:AddBlank(3)
                        di:Resize()
                        if ((#dx:GetChildren() == 2) or (4976 < 1332)) then
                            di:Show()
                        end
                        return di
                    end
                    di["Tabboxes"][an["Name"] or ""] = dw
                    return dw
                end
                di.AddLeftTabbox = function(self, dh)
                    return di:AddTabbox({Name = dh, Side = 1})
                end
                di.AddRightTabbox = function(self, dh)
                    return di:AddTabbox({Name = dh, Side = 2})
                end
                dk["InputBegan"]:Connect(
                    function(M)
                        if ((4628 == 4628) and (M["UserInputType"] == Enum["UserInputType"]["MouseButton1"])) then
                            di:ShowTab()
                        end
                    end
                )
                if ((#df:GetChildren() == 1) or (54 == 395)) then
                    di:ShowTab()
                end
                d9["Tabs"][dh] = di
                return di
            end
            local dA =
                s:Create(
                "TextButton",
                {
                    BackgroundTransparency = 1,
                    Size = UDim2.new(0, 0, 0, 0),
                    Visible = true,
                    Text = "",
                    Modal = false,
                    Parent = r
                }
            )
            local dB = {}
            local dC = false
            local dD = false
            s["MenuToggled"] = false
            s.Toggle = function(self)
                if dD then
                    return
                end
                local dE = d8["MenuFadeTime"]
                dD = true
                dC = not dC
                s["MenuToggled"] = dC
                dA["Modal"] = dC
                if dC then
                    bD["Visible"] = true
                    task.spawn(
                        function()

end)
end
                for D, dH in next, bD:GetDescendants() do
                    local F = {}
                    if ((82 == 82) and dH:IsA("ImageLabel")) then
                        table.insert(F, "ImageTransparency")
                        table.insert(F, "BackgroundTransparency")
                    elseif (dH:IsA("TextLabel") or dH:IsA("TextBox")) then
                        table.insert(F, "TextTransparency")
                    elseif (dH:IsA("Frame") or dH:IsA("ScrollingFrame")) then
                        table.insert(F, "BackgroundTransparency")
                    elseif dH:IsA("UIStroke") then
                        table.insert(F, "Transparency")
                    end
                    local dI = dB[dH]
                    if not dI then
                        dI = {}
                        dB[dH] = dI
                    end
                    for D, dJ in next, F do
                        if not dI[dJ] then
                            dI[dJ] = dH[dJ]
                        end
                        if (dI[dJ] == 1) then
                        else
                            m:Create(dH, TweenInfo.new(dE, Enum["EasingStyle"].Linear), {[dJ] = ((dC and dI[dJ]) or 1)}):Play(

                            )
                        end
                    end
                end
                task.wait(dE)
                bD["Visible"] = dC
                if ((s["MenuKeybind"] and (s["MenuKeybind"]["Type"] == "KeyPicker")) or (581 < 282)) then
                    s["MenuKeybind"]["Toggled"] = dC
                    s["MenuKeybind"]:Update()
                end
                dD = false
            end
            s:GiveSignal(
                g["InputBegan"]:Connect(
                    function(M, b9)
                        if (b9 or g:GetFocusedTextBox() or (4609 < 2495)) then
                            return
                        end
                        if ((type(s.ToggleKeybind) == "table") and (s["ToggleKeybind"]["Type"] == "KeyPicker")) then
                            if
                                ((M["UserInputType"] == Enum["UserInputType"]["Keyboard"]) and
                                    (M["KeyCode"]["Name"] == s["ToggleKeybind"]["Value"]))
                             then
                                task.spawn(s.Toggle)
                            end
                        elseif
                            ((M["KeyCode"] == Enum["KeyCode"]["RightControl"]) or
                                (M["KeyCode"] == Enum["KeyCode"]["RightShift"]))
                         then
                            task.spawn(s.Toggle)
                        end
                    end
                )
            )
            if d8["AutoShow"] then
                task.spawn(s.Toggle)
            end
            d9["Holder"] = bD
            return d9
        end
        local function dK()
            local v = u()
            for D, I in next, Options do
                if ((1152 == 1152) and (I["Type"] == "Dropdown") and (I["SpecialType"] == "Player")) then
                    I:SetValues(v)
                end
            end
        end
        k["PlayerAdded"]:Connect(dK)
        k["PlayerRemoving"]:Connect(dK)
        getgenv()["Library"] = s
        return s
    end,
    Api_Desync = function()
        return function(dL)
            local dM = {}
            local dN, dO, dP = dL["lp"], dL["heart"], dL["rnd"]
            local dQ = dL["cf"]
            local typeof = typeof
            local hookmetamethod, newcclosure, checkcaller = hookmetamethod, newcclosure, checkcaller
            local dR = {Enable = false, target = nil, real = nil, hooked = false, follow = false, conn = nil}
            do
                dM.validate = function(self)
                    local dS = dN["Character"]
                    if ((1896 <= 3422) and not dS) then
                        return false
                    end
                    local dT = dS:FindFirstChildOfClass("Humanoid")
                    if (not dT or (dT["Health"] <= 0) or (990 > 1620)) then
                        return false
                    end
                    return dT["RootPart"] ~= nil
                end
                dM.getRoot = function(self)
                    local dS = dN["Character"]
                    if not dS then
                        return nil
                    end
                    local dT = dS:FindFirstChildOfClass("Humanoid")
                    return dT and dT["RootPart"]
                end
                dM.parseCF = function(self, dU, dV, dW)
                    local dX = typeof(dU)
                    if ((dX == "CFrame") or (877 > 4695)) then
                        return dU
                    elseif ((2691 >= 1851) and (dX == "Vector3")) then
                        return dQ(dU.X, dU.Y, dU.Z)
                    elseif ((dX == "table") and dU[1] and dU[2] and dU[3]) then
                        return dQ(dU[1], dU[2], dU[3])
                    elseif ((dX == "number") and (type(dV) == "number") and (type(dW) == "number")) then
                        return dQ(dU, dV, dW)
                    end
                    return nil
                end
            end
            do
                local function dY()
                    if (dR["hooked"] or (2985 >= 4856)) then
                        return
                    end
                    if ((4276 >= 1195) and (not hookmetamethod or not newcclosure or not checkcaller)) then
                        dR["hooked"] = true
                        return
                    end
                    local dZ
                    dZ =
                        hookmetamethod(
                        game,
                        "__index",
                        (
                            newcclosure(
                                function(self, d_)
                                    if ((3232 <= 4690) and not checkcaller() and (d_ == "CFrame") and dR["Enable"]) then
                                        local e0 = dM:getRoot()
                                        if (e0 and (self == e0) and dR["real"]) then
                                            return dR["real"]
                                        end
                                    end
                                    return dZ(self, d_)
                                end
                            )
                        )
                    )
                    dR["hooked"] = true
                end
                dM.installHook = function(self)
                    dY()
                end
            end
            do
                local function e1()
                    if (dR["conn"] or (896 >= 3146)) then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
(


                            newcclosure(
                                function()
                                    if ((3061 >= 2958) and not dR["Enable"]) then
                                        return
                                    end
                                    if not dM:validate() then
                                        return
                                    end
                                    local e0 = dM:getRoot()
                                    if not e0 then
                                        return
                                    end
                                    dR["real"] = e0["CFrame"]
                                    local e2 = (dR["follow"] and e0["CFrame"]) or dR["target"] or dR["real"]
                                    e0["CFrame"] = e2
                                    dP:Wait()
                                    e0["CFrame"] = dR["real"]
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if dR["conn"] then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                end
                dM.startLoop = function(self)
                    e1()
                end
                dM.stopLoop = function(self)
                    e3()
                end
            end
            dM.moveTo = function(self, dU, dV, dW)
                local e2 = self:parseCF(dU, dV, dW)
                if not e2 then
                    return nil
                end
                dR["target"] = e2
                dR["follow"] = false
                dR["Enable"] = true
                self:installHook()
                self:startLoop()
                return e2
            end
            dM.syncWithPlayer = function(self)
                if ((3187 >= 644) and not self:validate()) then
                    return nil
                end
                dR["target"] = nil
                dR["follow"] = true
                dR["Enable"] = true
                self:installHook()
                self:startLoop()
                local e0 = self:getRoot()
                return (e0 and e0["CFrame"]) or nil
            end
            dM.stop = function(self)
                dR["Enable"] = false
                dR["target"] = nil
                dR["follow"] = false
                if ((644 <= 704) and dR["conn"]) then
                    pcall(
                        function()
                            dR["conn"]:Disconnect()
                        end
                    )
                    dR["conn"] = nil
                end
            end
            dM.isEnable = function(self)
                return dR["Enable"]
            end
            dM.getPosition = function(self)
                return (dR["target"] and dR["target"]["Position"]) or (self:getRoot() and self:getRoot()["Position"])
            end
            dM.getState = function(self)
                return dR["Enable"]
            end
            return dM
        end
    end,
    Api_Hooks = function()
        return function(dL)
            local e4 = {}
            local e5 = dL["replicatedstorage"]
            local C = e5:WaitForChild("MainEvent")
            local e6, e7 = false, {}
            local function dY()
                if ((958 > 947) and e6) then
                    return
                end
                e6 = true
                local e8 = getrawmetatable(C)
                setreadonly(e8, false)
                local e9 = table.clone(e8)
                local dZ = e9["__namecall"]
                setrawmetatable(
                    C,
                    {
                        __namecall = (
                            newcclosure(
                                function(self, ...)
                                    local ea = {...}
                                    if ((4492 >= 2654) and (getnamecallmethod() == "FireServer")) then
                                        for D, eb in pairs(e7) do
                                            pcall(eb, ea)
                                        end
                                    end
                                    return dZ(self, unpack(ea))
                                end
                            )
                        ),
                        __index = e9["__index"],
                        __newindex = e9["__newindex"],
                        __call = e9["__call"],
                        __tostring = e9["__tostring"]
                    }
                )
            end
            e4.register = function(self, ec, eb)
                if not e6 then
                    dY()
                end
                e7[ec] = eb
            end
            e4.unregister = function(self, ec)
                e7[ec] = nil
            end
            return e4
        end
    end,
    Api_Targeting = function()
        return function(dL)
            local ed = {}
            local ee, ef, eg, eh = dL["players"], dL["workspace"], dL["userinput"], dL["camera"]
            local dN = dL["lp"]
            local ei, ej = dL["huge"], dL["v2"]
            local ek, el = dL["insert"], dL["floor"]
            ed["target"] = nil
            ed["targetPlayer"] = nil
            ed["characterConn"] = nil
            ed["friendsList"] = {}
            ed["keepAfterDeath"] = true
            local function em(en)
                local D, eo = eh:WorldToViewportPoint(en)
                return eo
            end
            local function ep(eq, er)
                if ((3442 >= 1503) and (not er or not er:FindFirstChild("HumanoidRootPart"))) then
                    return true
                end
                local es = RaycastParams.new()
                es["FilterType"] = Enum["RaycastFilterType"]["Blacklist"]
                es["FilterDescendantsInstances"] = {dN["Character"], er}
                local et = (er["HumanoidRootPart"]["Position"] - eq)["Unit"] * 500
                local aW = ef:Raycast(eq, et, es)
                return aW ~= nil
            end
            local function eu(dS)
                if (not dS or not dS:FindFirstChild("HumanoidRootPart")) then
                    return ei
                end
                local ev = dS["HumanoidRootPart"]
                local ew, eo = eh:WorldToViewportPoint(ev.Position)
                if not eo then
                    return ei
                end
                local ex = eg:GetMouseLocation()
                local ey = ej(ew.X, ew.Y)
                return (ex - ey)["Magnitude"]
            end
            local function ez(dS)
                if (not dS or not dS:FindFirstChild("HumanoidRootPart")) then
                    return ei
                end
                if (not dN["Character"] or not dN["Character"]:FindFirstChild("HumanoidRootPart")) then
                    return ei
                end
                local eA = dN["Character"]["HumanoidRootPart"]["Position"]
                return (eA - dS["HumanoidRootPart"]["Position"])["Magnitude"]
            end
            local function eB(dS, eC)
                if (not dS or (3170 <= 1464)) then
                    return false
                end
                if (not eC or (4797 == 4388)) then
                    return true
                end
                local dT = dS:FindFirstChildOfClass("Humanoid")
                local eD = dS:FindFirstChild("BodyEffects")
                if eC["Visible"] then
                    local ev = dS:FindFirstChild("HumanoidRootPart")
                    if ((551 <= 681) and not ev) then
                        return false
                    end
                    if not em(ev.Position) then
                        return false
                    end
                    if (dN["Character"] and dN["Character"]:FindFirstChild("HumanoidRootPart")) then
                        if ep(dN["Character"]["HumanoidRootPart"].Position, dS) then
                            return false
                        end
                    end
                end
                if ((3277 > 407) and eC["Protect"]) then
                    if dS:FindFirstChild("ForceField") then
                        return false
                    end
                    if ((4695 >= 1415) and dS:FindFirstChild("ForceField_TESTING")) then
                        return false
                    end
                end
                if (eC["KO"] or (3212 <= 944)) then
                    local eE = false
                    if (eD and eD:FindFirstChild("K.O")) then
                        eE = eD["K.O"]["Value"] == true
                    end
                    if (dT and (dT["Health"] <= 0)) then
                        eE = true
                    end
                    if (eE or (3096 <= 1798)) then
                        return false
                    end
                end
                if eC["Dead"] then
                    if (eD and eD:FindFirstChild("SDeath")) then
                        if (eD["SDeath"]["Value"] ~= true) then
                        else
                            return false
                        end
                    end
                end
                if eC["Grabbed"] then
                    if dS:FindFirstChild("GRABBING_CONSTRAINT") then
                        return false
                    end
                end
                return true
            end
            ed.pickTarget = function(self, eF, eG, eC)
                local eH = nil
                local eI = ei
                eG = eG or "Mouse"
                for D, eJ in pairs(ee:GetPlayers()) do
                    if ((eJ ~= dN) and eJ["Character"]) then
                        local eK = false
                        if (eC and eC["Friend"] and self["friendsList"][eJ["Name"]]) then
                            eK = true
                        end
                        if (not eK and not eB(eJ.Character, eC)) then
                            eK = true
                        end
                        if not eK then
                            local eL
                            if (eG == "Distance") then
                                eL = ez(eJ.Character)
                            else
                                eL = eu(eJ.Character)
                                if (eF and (eL > eF)) then
                                    eL = nil
                                end
                            end
                            if (eL and (eL < eI)) then
                                eI = eL
                                eH = eJ["Character"]
                            end
                        end
                    end
                end
                if ((3537 == 3537) and eH) then
                    self["target"] = eH
                    local eM = self:getTargetPlayer()
                    if eM then
                        self:setupCharacterTracking(eM)
                    end
                end
                return eH
            end
            ed.resetTarget = function(self)
                if ((3837 >= 1570) and self["target"]) then
                    local eM = self:getTargetPlayer()
                    if eM then
                    end
                end
                if self["characterConn"] then
                    self["characterConn"]:Disconnect()
                    self["characterConn"] = nil
                end
                self["target"] = nil
                self["targetPlayer"] = nil
            end
            ed.getTarget = function(self)
                return self["target"]
            end
            ed.checkTarget = function(self)
                if (not self["target"] or (2950 == 3812)) then
                    return false
                end
                if ((4723 >= 2318) and not self["target"]["Parent"]) then
                    if (not self["keepAfterDeath"] or (2027 > 2852)) then
                        self:resetTarget()
                    end
                    return false
                end
                return true
            end
            ed.checkTargetHP = function(self)
                if not self["target"] then
                    return 0, 0
                end
                local dT = self["target"]:FindFirstChildOfClass("Humanoid")
                if (not dT or (1136 > 4317)) then
                    return 0, 0
                end
                return el(dT.Health), el(dT.MaxHealth)
            end
            ed.checkTargetLastHP = function(self)
                local eN, eO = self:checkTargetHP()
                return eN
            end
            ed.checkTargetTools = function(self)
                if ((4748 == 4748) and not self["target"]) then
                    return {}
                end
                local eP = {}
                for D, eQ in pairs(self["target"]:GetChildren()) do
                    if ((3736 <= 4740) and eQ:IsA("Tool")) then
                        ek(eP, eQ.Name)
                    end
                end
                return eP
            end
            ed.checkTargetHasTool = function(self, eR)
                if (not self["target"] or (3390 <= 3060)) then
                    return false
                end
                for D, eQ in pairs(self["target"]:GetChildren()) do
                    if ((eQ:IsA("Tool") and (eQ["Name"] == eR)) or (999 > 2693)) then
                        return true
                    end
                end
                return false
            end
            ed.checkTargetKnocked = function(self)
                if ((463 < 601) and not self["target"]) then
                    return false
                end
                local eD = self["target"]:FindFirstChild("BodyEffects")
                if (not eD or (2183 < 687)) then
                    return false
                end
                local eS = eD:FindFirstChild("K.O")
                if ((4549 == 4549) and eS and (eS["Value"] == true)) then
                    return true
                end
                local dT = self["target"]:FindFirstChildOfClass("Humanoid")
                if ((4672 == 4672) and dT and (dT["Health"] <= 0)) then
                    return true
                end
                return false
            end
            ed.checkTargetDead = function(self)
                if (not self["target"] or (3668 < 395)) then
                    return false
                end
                local eD = self["target"]:FindFirstChild("BodyEffects")
                if not eD then
                    return false
                end
                local eT = eD:FindFirstChild("SDeath")
                if ((eT and (eT["Value"] == true)) or (4166 == 455)) then
                    return true
                end
                return false
            end
            ed.checkTargetProtected = function(self)
                if not self["target"] then
                    return false
                end
                if (self["target"]:FindFirstChild("ForceField") or (4449 == 2663)) then
                    return true
                end
                if (self["target"]:FindFirstChild("ForceField_TESTING") or (4277 < 2989)) then
                    return true
                end
                return false
            end
            ed.checkTargetGrabbed = function(self)
                if (not self["target"] or (870 >= 4149)) then
                    return false
                end
                if self["target"]:FindFirstChild("GRABBING_CONSTRAINT") then
                    return true
                end
                return false
            end
            ed.getTargetDistance = function(self)
                if ((2212 < 3183) and not self["target"]) then
                    return ei
                end
                return ez(self.target)
            end
            ed.getTargetMouseDistance = function(self)
                if not self["target"] then
                    return ei
                end
                return eu(self.target)
            end
            ed.getTargetPart = function(self, eU)
                if ((4646 > 2992) and not self["target"]) then
                    return nil
                end
                return self["target"]:FindFirstChild(eU)
            end
            ed.getTargetPlayer = function(self)
                if ((1434 < 3106) and not self["target"]) then
                    return nil
                end
                for D, eJ in pairs(ee:GetPlayers()) do
                    if ((786 < 3023) and (eJ["Character"] == self["target"])) then
                        return eJ
                    end
                end
                return nil
            end
            ed.setupCharacterTracking = function(self, eV)
                if self["characterConn"] then
                    self["characterConn"]:Disconnect()
                    self["characterConn"] = nil
                end
                self["targetPlayer"] = eV
                self["characterConn"] =
                    eV["CharacterAdded"]:Connect(
                    function(eW)
                        if (not self["keepAfterDeath"] or (2442 < 74)) then
                            return
                        end
                        local dT = eW:WaitForChild("Humanoid", 5)
                        if not dT then
                            return
                        end
                        self["target"] = eW
                    end
                )
            end
            ed.addFriend = function(self, ec)
                if ((4535 == 4535) and (not ec or (ec == ""))) then
                    return false
                end
                self["friendsList"][ec] = true
                return true
            end
            ed.removeFriend = function(self, ec)
                if (not ec or (ec == "") or (3009 <= 2105)) then
                    return false
                end
                if ((1830 < 3669) and self["friendsList"][ec]) then
                    self["friendsList"][ec] = nil
                    return true
                end
                return false
            end
            ed.isFriend = function(self, ec)
                return self["friendsList"][ec] == true
            end
            ed.getFriendsList = function(self)
                local eX = {}
                for ec, D in pairs(self.friendsList) do
                    ek(eX, ec)
                end
                table.sort(eX)
                return eX
            end
            ed.clearFriends = function(self)
                self["friendsList"] = {}
            end
            ed.setKeepAfterDeath = function(self, eY)
                self["keepAfterDeath"] = eY
            end
            ed.getKeepAfterDeath = function(self)
                return self["keepAfterDeath"]
            end
            ed.init = function(self)
                ee["PlayerRemoving"]:Connect(
                    function(eJ)
                        if (self["target"] and (eJ["Character"] == self["target"])) then
                            if (not self["keepAfterDeath"] or (1430 >= 3612)) then
                                self["target"] = nil
                            end
                        end
                    end
                )
            end
            return ed
        end
    end,
    Api_LPH_Init = function()
        return function()
            local eZ = {}
            return eZ
        end
    end,
    Api_Services = function()
        local cloneref = cloneref or function(e_)
                return e_
            end
        return function()
            local dL = {}
            do
                dL["players"] = cloneref(game:GetService("Players"))
                dL["runservice"] = cloneref(game:GetService("RunService"))
                dL["userinput"] = cloneref(game:GetService("UserInputService"))
                dL["tweenservice"] = cloneref(game:GetService("TweenService"))
                dL["replicatedstorage"] = cloneref(game:GetService("ReplicatedStorage"))
                dL["http"] = cloneref(game:GetService("HttpService"))
                dL["teleport"] = cloneref(game:GetService("TeleportService"))
                dL["soundservice"] = cloneref(game:GetService("SoundService"))
                dL["workspace"] = game:GetService("Workspace")
                dL["lp"] = dL["players"]["LocalPlayer"]
                dL["mouse"] = dL["lp"]:GetMouse()
                dL["camera"] = dL["workspace"]["CurrentCamera"]
                dL["heart"] = dL["runservice"]["Heartbeat"]
                dL["rnd"] = dL["runservice"]["RenderStepped"]
                dL["random"] = math["random"]
                dL["huge"] = math["huge"]
                dL["floor"] = math["floor"]
                dL["ceil"] = math["ceil"]
                dL["abs"] = math["abs"]
                dL["min"] = math["min"]
                dL["max"] = math["max"]
                dL["sin"] = math["sin"]
                dL["cos"] = math["cos"]
                dL["rad"] = math["rad"]
                dL["deg"] = math["deg"]
                dL["insert"] = table["insert"]
                dL["remove"] = table["remove"]
                dL["find"] = table["find"]
                dL["clear"] = table["clear"]
                dL["v2"] = Vector2["new"]
                dL["v3"] = Vector3["new"]
                dL["c3"] = Color3["new"]
                dL["c3rgb"] = Color3["fromRGB"]
                dL["c3hex"] = Color3["fromHex"]
                dL["cf"] = CFrame["new"]
                dL["angles"] = CFrame["Angles"]
                dL["nr"] = NumberRange["new"]
                dL["ns"] = NumberSequence["new"]
                dL["nsk"] = NumberSequenceKeypoint["new"]
                dL["cs"] = ColorSequence["new"]
                dL["csk"] = ColorSequenceKeypoint["new"]
                dL["udim2"] = UDim2["new"]
                dL["stats"] = game:GetService("Stats")
                dL["new"] = Instance["new"]
                dL["spawn"] = task["spawn"]
                dL["wait"] = task["wait"]
                dL["delay"] = task["delay"]
                dL["format"] = string["format"]
                dL["lower"] = string["lower"]
                dL["upper"] = string["upper"]
                dL["sub"] = string["sub"]
                dL["gsub"] = string["gsub"]
                dL["match"] = string["match"]
                dL["draw"] = Drawing
            end
            return dL
        end
    end,
    Ragebot_AutoShoot = function()
        return function(dL)
            local f0 = {}
            local dN, dO, f1 = dL["lp"], dL["heart"], dL["random"]
            local ed = dL["targeting"]
            local f2 = dL["v3"]
            local f3 = dL["replicatedstorage"]:WaitForChild("MainEvent")
            local dR = {
                Enable = false,
                shootCooldown = 0.1,
                originMode = "Syncpos",
                upperDistance = 3,
                lastShootTime = 0,
                conn = nil
            }
            local function f4(f5)
                if (not f5 or not f5["Character"]) then
                    return false
                end
                local f6 = f5["Character"]:FindFirstChild("Head")
                if not f6 then
                    return false
                end
                local eD = f5["Character"]:FindFirstChild("BodyEffects")
                local f7 = f5["Character"]:FindFirstChild("Humanoid")
                local f8 = false
                if ((2683 >= 2460) and eD and eD:FindFirstChild("K.O")) then
                    f8 = eD["K.O"]["Value"] == true
                end
                if (f7 and (f7["Health"] <= 0)) then
                    f8 = true
                end
                local f9 = f5["Character"]:FindFirstChild("ForceField")
                local fa = eD and eD:FindFirstChild("SDeath") and (eD["SDeath"]["Value"] == true)
                local fb = f5["Character"]:FindFirstChild("GRABBING_CONSTRAINT") ~= nil
                if (f8 or fa or fb) then
                    return false
                end
                return true, f6, f9
            end
            local function fc(f6)
                if ((dR["originMode"] == "Syncpos") or (1804 >= 3275)) then
                    return f6["Position"] + f2(0, 3, 0)
                elseif ((dR["originMode"] == "Upper") or (1417 > 3629)) then
                    return f6["Position"] + f2(0, dR.upperDistance, 0)
                elseif ((4795 > 402) and (dR["originMode"] == "Random")) then
                    local fd = f1(1, 3) * (((f1(0, 1) == 0) and -1) or 1)
                    local fe = f1(1, 3) * (((f1(0, 1) == 0) and -1) or 1)
                    local ff = f1(1, 3) * (((f1(0, 1) == 0) and -1) or 1)
                    return f6["Position"] + f2(fd, fe, ff)
                end
                return f6["Position"] + f2(0, 3, 0)
            end
            do
                local function fg()
                    if ((4813 > 3565) and not dR["Enable"]) then
                        return
                    end
                    local fh = tick()
                    if ((fh - dR["lastShootTime"]) >= dR["shootCooldown"]) then
                    else
                        return
                    end
                    local f5 = ed:getTargetPlayer()
                    if not f5 then
                        return
                    end
                    local fi, f6, f9 = f4(f5)
                    if not fi then
                        return
                    end
                    if not dN["Character"] then
                        return
                    end
                    local fj = fc(f6)
                    local fk = false
                    for D, fl in ipairs(dN["Character"]:GetChildren()) do
                        if (fl:IsA("Tool") and fl:FindFirstChild("Handle")) then
                            if ((3912 == 3912) and (not f9 or (fl["Name"] == "[Rifle]"))) then
                                pcall(
                                    function()
                                        f3:FireServer("ShootGun", fl.Handle, fj, f6.Position, f6, f2(0, 0, 0))
                                    end
                                )
                                fk = true
                            end
                        end
                    end
                    if ((2821 <= 4824) and fk) then
                        dR["lastShootTime"] = fh
                    end
                end
                local function e1()
                    if dR["conn"] then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function()
                                    fg()
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if ((1738 <= 2195) and dR["conn"]) then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if ((41 <= 3018) and eY) then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setShootCooldown = function(self, fm)
                dR["shootCooldown"] = fm / 1000
            end
            f0.setOriginMode = function(self, eG)
                dR["originMode"] = eG
            end
            f0.setUpperDistance = function(self, fn)
                dR["upperDistance"] = fn
            end
            f0.init = function(self)
                dR["shootCooldown"] = 0.1 / 1000
            end
            return f0
        end
    end,
    Ragebot_DesyncAutoBuy = function()
        return function(dL)
            local f0 = {}
            local dN, ef, fo, wait = dL["lp"], dL["workspace"], dL["spawn"], dL["wait"]
            local ed = dL["targeting"]
            local dR = {
                Enable = false,
                armorEnable = false,
                gunsEnable = false,
                ammoEnable = false,
                selectedGuns = {},
                conn = nil,
                buyingInProgress = false,
                conditions = {noTarget = false, targetAlive = false, targetForcefielded = false}
            }
            local fp = ef["Ignored"]["Shop"]
            local fq = fp["[High-Medium Armor] - $2513"]
            local fr = {
                {Name = "[Rifle]", ShopName = "[Rifle] - $1694", AmmoShop = "5 [Rifle Ammo] - $273"},
                {Name = "[LMG]", ShopName = "[LMG] - $4098", AmmoShop = "200 [LMG Ammo] - $328"},
                {Name = "[P90]", ShopName = "[P90] - $1093", AmmoShop = "120 [P90 Ammo] - $66"},
                {Name = "[Flintlock]", ShopName = "[Flintlock] - $1421", AmmoShop = "6 [Flintlock Ammo] - $163"},
                {Name = "[Revolver]", ShopName = "[Revolver] - $1421", AmmoShop = "12 [Revolver Ammo] - $82"},
                {
                    Name = "[Double-Barrel SG]",
                    ShopName = "[Double-Barrel SG] - $1475",
                    AmmoShop = "18 [Double-Barrel SG Ammo] - $66"
                },
                {Name = "[AK47]", ShopName = "[AK47] - $2459", AmmoShop = "90 [AK47 Ammo] - $87"},
                {
                    Name = "[TacticalShotgun]",
                    ShopName = "[TacticalShotgun] - $1912",
                    AmmoShop = "20 [TacticalShotgun Ammo] - $66"
                },
                {Name = "[SMG]", ShopName = "[SMG] - $820", AmmoShop = "80 [SMG Ammo] - $66"},
                {Name = "[AR]", ShopName = "[AR] - $1093", AmmoShop = "100 [AR Ammo] - $82"},
                {Name = "[Silencer]", ShopName = "[Silencer] - $437", AmmoShop = "25 [Silencer Ammo] - $55"},
                {Name = "[Shotgun]", ShopName = "[Shotgun] - $1366", AmmoShop = "20 [Shotgun Ammo] - $66"},
                {Name = "[AUG]", ShopName = "[AUG] - $2131", AmmoShop = "90 [AUG Ammo] - $87"}
            }
            do
                f0.checkConditions = function(self)
                    if ((2145 <= 4104) and dR["conditions"]["noTarget"]) then
                        if ((2689 < 4845) and not ed["target"]) then
                            return false
                        end
                    end
                    if dR["conditions"]["targetAlive"] then
                        if ed["target"] then
                            local eE = ed:checkTargetKnocked()
                            local fs = ed:checkTargetDead()
                            if (not eE and not fs) then
                                return false
                            end
                        end
                    end
                    if (dR["conditions"]["targetForcefielded"] or (2322 > 2622)) then
                        if ed["target"] then
                            local ft = ed:checkTargetProtected()
                            if (ft or (4534 == 2082)) then
                                return false
                            end
                        end
                    end
                    return true
                end
                f0.getCurrentArmor = function(self)
                    local fu = ef:FindFirstChild("Players")
                    if (not fu or (1571 > 1867)) then
                        return 0
                    end
                    local fv = fu:FindFirstChild(dN.Name)
                    if not fv then
                        return 0
                    end
                    local eD = fv:FindFirstChild("BodyEffects")
                    if (not eD or (2654 >= 2996)) then
                        return 0
                    end
                    local fw = eD:FindFirstChild("Armor")
                    if ((3978 > 2104) and not fw) then
                        return 0
                    end
                    return tonumber(fw.Value) or 0
                end
                f0.hasWeapon = function(self, fx)
                    if ((2995 > 1541) and dN["Backpack"]:FindFirstChild(fx)) then
                        return true
                    end
                    if (dN["Character"] and dN["Character"]:FindFirstChild(fx)) then
                        return true
                    end
                    return false
                end
                f0.getWeaponAmmo = function(self, fx)
                    local fy = dN["DataFolder"]["Inventory"]:FindFirstChild(fx)
                    return (fy and tonumber(fy.Value)) or 0
                end
            end
            do
                f0.buyArmor = function(self)
                    if (not dR["armorEnable"] or dR["buyingInProgress"]) then
                        return
                    end
                    if (not dN["Character"] or not dN["Character"]:FindFirstChild("HumanoidRootPart")) then
                        return
                    end
                    if not self:checkConditions() then
                        return
                    end
                    local fz = self:getCurrentArmor()
                    if ((3249 > 953) and (fz >= 130)) then
                        return
                    end
                    dR["buyingInProgress"] = true
                    local B =
                        pcall(
                        function()
                            repeat
                                for D, fl in pairs(dN["Character"]:GetChildren()) do
                                    if (fl:IsA("Tool") or (3273 > 4573)) then
                                        fl["Parent"] = dN["Backpack"]
                                    end
                                end
                                dL["desync"]:moveTo(
                                    fq["Head"]["Position"].X,
                                    fq["Head"]["Position"].Y,
                                    fq["Head"]["Position"].Z
                                )
                                fireclickdetector(fq.ClickDetector)
                                wait(0.1)
                                fz = self:getCurrentArmor()
                            until fz >= 130
                        end
                    )
                    dR["buyingInProgress"] = false
                    dL["desync"]:syncWithPlayer()
                    if not B then

                    end
                end
                f0.buyGuns = function(self)
                    if (not dR["gunsEnable"] or dR["buyingInProgress"]) then
                        return
                    end
                    if (not dN["Character"] or not dN["Character"]:FindFirstChild("HumanoidRootPart") or (3151 < 1284)) then
                        return
                    end
                    if not self:checkConditions() then
                        return
                    end
                    local fA = false
                    for D, fB in pairs(dR.selectedGuns) do
                        if not self:hasWeapon(fB) then
                            fA = true
                            break
                        end
                    end
                    if not fA then
                        return
                    end
                    dR["buyingInProgress"] = true
                    local B =
                        pcall(
                        function()
                            for D, fB in pairs(dR.selectedGuns) do
                                if (not self:hasWeapon(fB) or (1850 == 1529)) then
                                    for D, fC in pairs(fr) do
                                        if (fC["Name"] ~= fB) then
                                        else
                                            local fD = fp:FindFirstChild(fC.ShopName)
                                            if ((821 < 2123) and fD) then
                                                local fE = fD:FindFirstChild("Head")
                                                local fF = fD:FindFirstChild("ClickDetector")
                                                if ((902 < 2325) and fE and fF) then
                                                    repeat
                                                        for D, fl in pairs(dN["Character"]:GetChildren()) do
                                                            if ((858 <= 2962) and fl:IsA("Tool")) then
                                                                fl["Parent"] = dN["Backpack"]
                                                            end
                                                        end
                                                        dL["desync"]:moveTo(
                                                            fE["Position"].X,
                                                            fE["Position"].Y,
                                                            fE["Position"].Z
                                                        )
                                                        fireclickdetector(fF)
                                                        wait(0.1)
                                                    until self:hasWeapon(fB)
                                                end
                                            end
                                            break
                                        end
                                    end
                                end
                            end
                        end
                    )
                    dR["buyingInProgress"] = false
                    dL["desync"]:syncWithPlayer()
                    if (not B or (3946 < 1288)) then

                    end
                end
                f0.buyAmmo = function(self)
                    if (not dR["ammoEnable"] or dR["buyingInProgress"]) then
                        return
                    end
                    if (not dN["Character"] or not dN["Character"]:FindFirstChild("HumanoidRootPart") or (3242 == 567)) then
                        return
                    end
                    if (not self:checkConditions() or (847 >= 1263)) then
                        return
                    end
                    local fA = false
                    for D, fB in pairs(dR.selectedGuns) do
                        if (self:hasWeapon(fB) or (2253 == 1851)) then
                            local fG = self:getWeaponAmmo(fB)
                            if (fG ~= 0) then
                            else
                                fA = true
                                break
                            end
                        end
                    end
                    if not fA then
                        return
                    end
                    dR["buyingInProgress"] = true
                    local B =
                        pcall(
                        function()
                            for D, fB in pairs(dR.selectedGuns) do
                                if self:hasWeapon(fB) then
                                    local fG = self:getWeaponAmmo(fB)
                                    if (fG ~= 0) then
                                    else
                                        for D, fC in pairs(fr) do
                                            if ((fC["Name"] == fB) or (2087 > 2372)) then
                                                local fH = fp:FindFirstChild(fC.AmmoShop)
                                                if fH then
                                                    local fE = fH:FindFirstChild("Head")
                                                    local fF = fH:FindFirstChild("ClickDetector")
                                                    if (fE and fF) then
                                                        repeat
                                                            for D, fl in pairs(dN["Character"]:GetChildren()) do
                                                                if fl:IsA("Tool") then
                                                                    fl["Parent"] = dN["Backpack"]
                                                                end
                                                            end
                                                            dL["desync"]:moveTo(
                                                                fE["Position"].X,
                                                                fE["Position"].Y,
                                                                fE["Position"].Z
                                                            )
                                                            fireclickdetector(fF)
                                                            wait(0.1)
                                                            fG = self:getWeaponAmmo(fB)
                                                        until fG > 0
                                                    end
                                                end
                                                break
                                            end
                                        end
                                    end
                                end
                            end
                        end
                    )
                    dR["buyingInProgress"] = false
                    dL["desync"]:syncWithPlayer()
                    if not B then

                    end
                end
            end
            do
                local function fI()
                    if (dR["conn"] or (4445 < 4149)) then
                        return
                    end
                    dR["conn"] =
                        fo(
                        function()
                            while dR["Enable"] do
                                if ((dR["armorEnable"] and not dR["buyingInProgress"]) or (1818 == 85)) then
                                    pcall(
                                        function()
                                            f0:buyArmor()
                                        end
                                    )
                                end
                                if (dR["gunsEnable"] and not dR["buyingInProgress"]) then
                                    pcall(
                                        function()
                                            f0:buyGuns()
                                        end
                                    )
                                end
                                if (dR["ammoEnable"] and not dR["buyingInProgress"]) then
                                    pcall(
                                        function()
                                            f0:buyAmmo()
                                        end
                                    )
                                end
                                wait(0.8)
                            end
                            dR["conn"] = nil
                        end
                    )
                end
                local function fJ()
                    if ((630 < 2127) and dR["conn"]) then
                        dR["conn"] = nil
                    end
                    dR["buyingInProgress"] = false
                end
                f0.startLoop = function(self)
                    fI()
                end
                f0.stopLoop = function(self)
                    fJ()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if eY then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setArmorEnable = function(self, eY)
                dR["armorEnable"] = eY
            end
            f0.setGunsEnable = function(self, eY)
                dR["gunsEnable"] = eY
            end
            f0.setAmmoEnable = function(self, eY)
                dR["ammoEnable"] = eY
            end
            f0.setSelectedGuns = function(self, fK)
                dR["selectedGuns"] = fK
            end
            f0.getGunsConfig = function(self)
                return fr
            end
            f0.setConditions = function(self, fL)
                dR["conditions"] = fL
            end
            f0.isBuyingInProgress = function(self)
                return dR["buyingInProgress"]
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_DesyncAutoStomp = function()
        return function(dL)
            local f0 = {}
            local dN, ef, dO = dL["lp"], dL["workspace"], dL["heart"]
            local ed = dL["targeting"]
            local f3 = dL["replicatedstorage"]:WaitForChild("MainEvent")
            local dR = {
                Enable = false,
                stompHeight = 2.7,
                conn = nil,
                wasStomping = false,
                lastStompTime = 0,
                lastSyncTime = 0,
                syncDelay = 0.1
            }
            local function fM()
                local B, fN =
                    pcall(
                    function()
                        return dN:GetNetworkPing() * 1000
                    end
                )
                return (B and fN) or 50
            end
            local function fO()
                if (dR["lastStompTime"] ~= 0) then
                else
                    return true
                end
                local fh = tick()
                local fP = fh - dR["lastStompTime"]
                local fQ = fM() / 1000
                return fP >= fQ
            end
            local function fR()
                if (dR["lastSyncTime"] ~= 0) then
                else
                    return true
                end
                local fh = tick()
                local fS = fh - dR["lastSyncTime"]
                local fQ = (fM() + 40) / 1000
                return fS >= fQ
            end
            do
                f0.canStomp = function(self)
                    if (not dN["Character"] or not dN["Character"]:FindFirstChild("HumanoidRootPart")) then
                        return false
                    end
                    local fT = dN["Character"]:FindFirstChild("BodyEffects")
                    if fT then
                        if (fT:FindFirstChild("Reload") and fT["Reload"]["Value"]) then
                            return false
                        end
                        if (fT:FindFirstChild("Attacking") and fT["Attacking"]["Value"]) then
                            return false
                        end
                    end
                    return true
                end
                f0.shouldStompTarget = function(self)
                    if (not ed["target"] or (1938 == 2514)) then
                        return false
                    end
                    local fa = ed:checkTargetDead()
                    if fa then
                        return false
                    end
                    local f8 = ed:checkTargetKnocked()
                    if ((4255 >= 55) and not f8) then
                        return false
                    end
                    local fb = ed["target"]:FindFirstChild("GRABBING_CONSTRAINT") ~= nil
                    if fb then
                        return false
                    end
                    return true
                end
            end
            do
                local function fU()
                    if not dR["Enable"] then
                        return
                    end
                    if not f0:canStomp() then
                        if ((2999 > 1156) and dR["wasStomping"] and fO()) then
                            dL["desync"]:syncWithPlayer()
                            dR["wasStomping"] = false
                            dR["lastStompTime"] = 0
                            dR["lastSyncTime"] = tick()
                        end
                        return
                    end
                    local fV = f0:shouldStompTarget()
                    if ((2350 > 1155) and not fV) then
                        if ((4029 <= 4853) and dR["wasStomping"] and fO()) then
                            dL["desync"]:syncWithPlayer()
                            dR["wasStomping"] = false
                            dR["lastStompTime"] = 0
                            dR["lastSyncTime"] = tick()
                        end
                        return
                    end
                    local fW = ed["target"]:FindFirstChild("UpperTorso")
                    if (not fW or (516 > 3434)) then
                        if ((4046 >= 3033) and dR["wasStomping"] and fO()) then
                            dL["desync"]:syncWithPlayer()
                            dR["wasStomping"] = false
                            dR["lastStompTime"] = 0
                            dR["lastSyncTime"] = tick()
                        end
                        return
                    end
                    local fX = fW["Position"] + dL.v3(0, dR.stompHeight, 0)
                    dL["desync"]:moveTo(fX.X, fX.Y, fX.Z)
                    dR["wasStomping"] = true
                    pcall(
                        function()
                            f3:FireServer("Stomp")
                            dR["lastStompTime"] = tick()
                        end
                    )
                end
                local function e1()
                    if dR["conn"] then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function()
                                    fU()
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if dR["conn"] then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    dL["desync"]:syncWithPlayer()
                    dR["wasStomping"] = false
                    dR["lastStompTime"] = 0
                    dR["lastSyncTime"] = 0
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if (eY or (2719 <= 1447)) then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setStompHeight = function(self, fY)
                dR["stompHeight"] = fY
            end
            f0.isStompingInProgress = function(self)
                return dR["Enable"] and f0:shouldStompTarget()
            end
            f0.canContinueDesync = function(self)
                return fO() and fR()
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_DesyncCSync = function()
        return function(dL)
            local f0 = {}
            local dN, dO = dL["lp"], dL["heart"]
            local ed = dL["targeting"]
            local f1, ei, fZ = dL["random"], dL["huge"], math["clamp"]
            local el, f_, g0 = dL["floor"], dL["sin"], dL["cos"]
            local tick = tick
            local dR = {
                Enable = false,
                mode = "Random",
                radiusX = 5,
                radiusY = 5,
                radiusZ = 5,
                useMinDistance = false,
                minDistanceX = 0,
                minDistanceY = 0,
                minDistanceZ = 0,
                spiralDistance = 10,
                spiralSpeed = 1,
                spiralYOffset = 0,
                spiralAngle = 0,
                spiralYZDistance = 10,
                spiralYZSpeed = 1,
                spiralYZXOffset = 0,
                spiralYZAngle = 0,
                spiralYXDistance = 10,
                spiralYXSpeed = 1,
                spiralYXZOffset = 0,
                spiralYXAngle = 0,
                baitSpiralDistance = 10,
                baitSpiralSpeed = 1,
                baitSpiralYOffset = 0,
                baitSpiralAngle = 0,
                baitCooldown = 0.5,
                baitDistance = 10,
                baitDirections = {},
                baitWait = 0.1,
                lastBaitTime = 0,
                isBaiting = false,
                baitWaitStartTime = 0,
                baitTargetPos = nil,
                predictEnable = false,
                predictMode = "Regular",
                predictStrength = 2,
                resolveEnable = false,
                resolveAggression = 1,
                lastTargetPosition = nil,
                lastTargetTime = nil,
                resolveData = {samples = {}, maxSamples = 10, avgVelocity = 0, avgPing = 0},
                calculateHistory = {},
                calculateHistorySize = 60,
                calculateBias = dL.v3(0, 0, 0),
                calculateVelWeight = 1,
                calculateAccWeight = 0.35,
                calculateAdaptRate = 0.06,
                calculateVelFilter = nil,
                calculateCorrect = 0,
                calculateTotal = 0,
                betterPoseHistory = {},
                betterPingDivisionFactor = 500,
                conn = nil,
                lastTarget = nil,
                wasActive = false,
                lastTargetLostTime = 0,
                lastSyncTime = 0,
                autoBuyModule = nil,
                autoStompModule = nil
            }
            local function fM()
                local B, fN =
                    pcall(
                    function()
                        return dN:GetNetworkPing() * 1000
                    end
                )
                return (B and fN) or 50
            end
            local function fO()
                if (dR["lastTargetLostTime"] ~= 0) then
                else
                    return true
                end
                local fh = tick()
                local g1 = fh - dR["lastTargetLostTime"]
                local fQ = fM() / 1000
                return g1 >= fQ
            end
            local function fR()
                if ((dR["lastSyncTime"] == 0) or (4134 < 3926)) then
                    return true
                end
                local fh = tick()
                local fS = fh - dR["lastSyncTime"]
                local fQ = (fM() + 20) / 1000
                return fS >= fQ
            end
            local function g2(g3, g4)
                local g5 = (g4 - g3)["Magnitude"]
                dR["calculateTotal"] = dR["calculateTotal"] + 1
                if ((g5 <= 1) or (g5 ~= g5)) then
                    dR["calculateCorrect"] = dR["calculateCorrect"] + 1
                end
                if ((g5 < 4) and (g5 == g5)) then
                    local g6 = (g4 - g3) * dR["calculateAdaptRate"]
                    dR["calculateBias"] = dR["calculateBias"] + g6
                end
                if (((g5 > 1.8) and (dR["calculateVelWeight"] > 0.7)) or (164 >= 2785)) then
                    dR["calculateVelWeight"] = fZ(dR["calculateVelWeight"] - 0.015, 0.7, ei)
                elseif ((g5 < 0.7) and (dR["calculateVelWeight"] < 1.4)) then
                    dR["calculateVelWeight"] = fZ(dR["calculateVelWeight"] + 0.01, 0, 1.4)
                end
            end
            local function g7()
                if ((#dR["calculateHistory"] < 4) or (525 == 2109)) then
                    return dR["calculateHistory"][#dR["calculateHistory"]]["pos"]
                end
                local g8 = dR["calculateHistory"]
                local g9 = g8[#g8]["pos"]
                local ga = g8[#g8 - 1]["pos"]
                local gb = g8[#g8]["time"] - g8[#g8 - 1]["time"]
                local gc = ((gb ~= 0) and (((g9 - ga) / gb) * dR["calculateVelWeight"])) or dL.v3(ei, ei, ei)
                local gd = dL.v3(0, 0, 0)
                if (#g8 < 3) then
                else
                    local ge =
                        (((g8[#g8 - 1]["time"] - g8[#g8 - 2]["time"]) ~= 0) and
                        ((ga - g8[#g8 - 2]["pos"]) / (g8[#g8 - 1]["time"] - g8[#g8 - 2]["time"]))) or
                        dL.v3(ei, ei, ei)
                    gd = ((gb ~= 0) and (((gc - ge) / gb) * dR["calculateAccWeight"])) or dL.v3(0, 0, 0)
                end
                dR["calculateVelFilter"] =
                    (dR["calculateVelFilter"] and (dR["calculateVelFilter"] + ((gc - dR["calculateVelFilter"]) * 0.7))) or
                    gc
                local gf = g9
                gf = gf + (dR["calculateVelFilter"] * gb)
                gf = gf + (gd * gb * gb)
                gf = gf + dR["calculateBias"]
                return gf
            end
            local function gg(gh)
                local fN = fM()
                dL.insert(dR["resolveData"].samples, {velocity = gh, ping = fN, time = tick()})
                if ((33 == 33) and (#dR["resolveData"]["samples"] > dR["resolveData"]["maxSamples"])) then
                    dL.remove(dR["resolveData"].samples, 1)
                end
                local gi = 0
                local gj = 0
                for D, gk in pairs(dR["resolveData"].samples) do
                    gi = gi + gk["velocity"]
                    gj = gj + gk["ping"]
                end
                dR["resolveData"]["avgVelocity"] = gi / #dR["resolveData"]["samples"]
                dR["resolveData"]["avgPing"] = gj / #dR["resolveData"]["samples"]
                local gl = 2
                local gm = fZ(dR["resolveData"]["avgVelocity"] / 5, 0, 10)
                local gn = fZ(dR["resolveData"]["avgPing"] / 40, 0, 5)
                local go = gl + gm + gn
                local gp = go * dR["resolveAggression"]
                return fZ(gp, 1, 100)
            end
            local function gq(gr, f5)
                if ((3054 <= 4015) and (not f5 or not f5:FindFirstChild("HumanoidRootPart"))) then
                    return
                end
                local fh = tick()
                local gs = f5:FindFirstChild("HumanoidRootPart")
                local gt = {}
                for D, gu in pairs(f5:GetDescendants()) do
                    if (gu:IsA("BasePart") and (gu ~= gs)) then
                        gt[gu["Name"]] = gs["CFrame"]:ToObjectSpace(gu.CFrame)
                    end
                end
                dL.insert(dR.betterPoseHistory, {Time = fh, Pivot = f5:GetPivot(), BodyPartsCFrames = gt})
                while (#dR["betterPoseHistory"] > 0) and ((fh - dR["betterPoseHistory"][1]["Time"]) > (1 / gr)) do
                    dL.remove(dR.betterPoseHistory, 1)
                end
            end
            local function gv(f5)
                if ((1871 < 3382) and (not f5 or (#dR["betterPoseHistory"] < 2))) then
                    return nil
                end
                local gw = dL["stats"]
                if not gw then
                    return nil
                end
                local gx = gw:FindFirstChild("Network")
                if ((1293 <= 2166) and not gx) then
                    return nil
                end
                local gy = gx:FindFirstChild("ServerStatsItem")
                if not gy then
                    return nil
                end
                local gz = gy:FindFirstChild("Data Ping")
                if (not gz or (2579 < 123)) then
                    return nil
                end
                local fh = tick()
                local gA = fZ(gz:GetValue() / dR["betterPingDivisionFactor"], 0, ei)
                local gB = dR["betterPoseHistory"][#dR["betterPoseHistory"]]
                local gC = dR["betterPoseHistory"][#dR["betterPoseHistory"] - 1]
                if (not gB or not gC or (846 >= 2368)) then
                    return nil
                end
                local gr = gB["Time"] - gC["Time"]
                if ((gr <= 0) or (4012 <= 3358)) then
                    return nil
                end
                local gD = (gB["Pivot"]["Position"] - gC["Pivot"]["Position"]) / gr
                local gE = gB["Pivot"]["Position"] + (gD * gA)
                return gE
            end
            local function gF(ey, gG)
                local gH = (gG - ey)["Unit"]
                local gI = f1(0, 360)
                local gJ = math.rad(gI)
                local gK = dR["baitDirections"]["X"] or false
                local gL = dR["baitDirections"]["Y"] or false
                local gM = dR["baitDirections"]["Z"] or false
                if ((1494 <= 3005) and not gK and not gL and not gM) then
                    gK, gL, gM = true, true, true
                end
                local fd = 0
                local fe = 0
                local ff = 0
                if gK then
                    fd = (((f1(0, 1) == 0) and -1) or 1) * dR["baitDistance"]
                end
                if (gL or (3111 == 2134)) then
                    fe = (((f1(0, 1) == 0) and -1) or 1) * dR["baitDistance"]
                end
                if ((2355 == 2355) and gM) then
                    ff = (((f1(0, 1) == 0) and -1) or 1) * dR["baitDistance"]
                end
                local gN = dL.v3(fd, fe, ff)
                if ((gN["Magnitude"] > 0) or (588 <= 432)) then
                    gN = gN["Unit"] * dR["baitDistance"]
                end
                return ey + gN
            end
            local function gO(en)
                if
                    ((4797 >= 3895) and
                        ((en["X"] == ei) or (en["X"] == -ei) or (en["Y"] == ei) or (en["Y"] == -ei) or (en["Z"] == ei) or
                            (en["Z"] == -ei)))
                 then
                    return true, "inf"
                end
                if ((3577 == 3577) and ((en["X"] ~= en["X"]) or (en["Y"] ~= en["Y"]) or (en["Z"] ~= en["Z"]))) then
                    return true, "nan"
                end
                return false, nil
            end
            do
                f0.shouldStopCSync = function(self)
                    if ((3794 > 3693) and not ed["target"]) then
                        return true
                    end
                    if (ed["target"]:FindFirstChild("ForceField") or (1275 == 4100)) then
                        return true
                    end
                    if ed["target"]:FindFirstChild("ForceField_TESTING") then
                        return true
                    end
                    local gP = ed["target"]:FindFirstChild("BodyEffects")
                    if (gP or (1591 >= 3580)) then
                        local gQ = gP:FindFirstChild("K.O")
                        if (gQ and (gQ["Value"] == true)) then
                            return true
                        end
                    end
                    local fa = ed:checkTargetDead()
                    if ((983 <= 1808) and fa) then
                        return true
                    end
                    return false
                end
            end
            do
                local function gR(gr)
                    if not dR["Enable"] then
                        return
                    end
                    if ((dR["predictEnable"] and (dR["predictMode"] == "Better") and ed["target"]) or (2150 <= 1197)) then
                        gq(gr, ed.target)
                    end
                    if (dR["autoBuyModule"] and dR["autoBuyModule"]:isBuyingInProgress()) then
                        return
                    end
                    if dR["autoStompModule"] then
                        if dR["autoStompModule"]:isStompingInProgress() then
                            return
                        end
                        if not dR["autoStompModule"]:canContinueDesync() then
                            return
                        end
                    end
                    if f0:shouldStopCSync() then
                        if ((3769 >= 1173) and dR["wasActive"]) then
                            if ((1485 == 1485) and (dR["lastTargetLostTime"] == 0)) then
                                dR["lastTargetLostTime"] = tick()
                            end
                            if fO() then
                                dL["desync"]:syncWithPlayer()
                                dR["wasActive"] = false
                                dR["lastTargetLostTime"] = 0
                                dR["lastSyncTime"] = tick()
                            end
                        end
                        dR["lastTarget"] = nil
                        return
                    end
                    local gS = ed["target"]:FindFirstChild("HumanoidRootPart")
                    if not gS then
                        if dR["wasActive"] then
                            if (dR["lastTargetLostTime"] ~= 0) then
                            else
                                dR["lastTargetLostTime"] = tick()
                            end
                            if (fO() or (3315 <= 2782)) then
                                dL["desync"]:syncWithPlayer()
                                dR["wasActive"] = false
                                dR["lastTargetLostTime"] = 0
                                dR["lastSyncTime"] = tick()
                            end
                        end
                        dR["lastTarget"] = nil
                        return
                    end
                    if ((dR["lastTarget"] ~= ed["target"]) or (876 >= 2964)) then
                        dR["lastTarget"] = ed["target"]
                    end
                    dR["wasActive"] = true
                    local ey = gS["Position"]
                    local gT, gU = gO(ey)
                    if gT then
                        if ((gU == "nan") or (2232 > 2497)) then
                            local dS = dN["Character"]
                            local ev = dS and dS:FindFirstChild("HumanoidRootPart")
                            if ev then
                                dL["desync"]:moveTo(ev["Position"].X, ev["Position"].Y, ev["Position"].Z)
                            end
                        elseif (gU == "inf") then
                            dL["desync"]:moveTo(ey.X, ey.Y, ey.Z)
                        end
                        return
                    end
                    if (dR["predictEnable"] or (2110 <= 332)) then
                        if (dR["predictMode"] == "Better") then
                            local gV = gv(ed.target)
                            if gV then
                                ey = gV
                            end
                        elseif ((3686 > 3172) and (dR["predictMode"] == "Regular")) then
                            local fh = tick()
                            if ((dR["lastTargetPosition"] and dR["lastTargetTime"]) or (4474 < 820)) then
                                local gr = fh - dR["lastTargetTime"]
                                if ((4279 >= 2882) and (gr > 0) and (gr < 1)) then
                                    if (((ey - dR["lastTargetPosition"])["Magnitude"] >= 0.001) or (2029 >= 3521)) then
                                        local gW = dR["predictStrength"]
                                        local gX = (ey - dR["lastTargetPosition"]) / gr
                                        local gh = gX["Magnitude"]
                                        if (dR["resolveEnable"] or (2037 >= 4642)) then
                                            gW = gg(gh)
                                        end
                                        local gY = gW * 0.01
                                        local fn = (ey - dR["lastTargetPosition"])["Magnitude"]
                                        local gZ = (fn / gr) * gY
                                        local g_ = (ey - dR["lastTargetPosition"])["Unit"]
                                        ey = ey + (g_ * gZ)
                                    end
                                end
                            end
                            dR["lastTargetPosition"] = gS["Position"]
                            dR["lastTargetTime"] = fh
                        elseif (dR["predictMode"] ~= "Calculate") then
                        else
                            local fh = tick()
                            dL.insert(dR.calculateHistory, {pos = ey, time = fh})
                            if ((1720 < 4458) and (#dR["calculateHistory"] > dR["calculateHistorySize"])) then
                                dL.remove(dR.calculateHistory, 1)
                            end
                            if ((#dR["calculateHistory"] >= 4) or (436 > 3021)) then
                                local h0 = g7()
                                if (#dR["calculateHistory"] < 2) then
                                else
                                    local ga = dR["calculateHistory"][#dR["calculateHistory"] - 1]
                                    if ga["predicted"] then
                                        g2(ga.predicted, ey)
                                    end
                                end
                                dR["calculateHistory"][#dR["calculateHistory"]]["predicted"] = h0
                                local fN = fM()
                                local h1 = (fN + 20) / 1000
                                local g8 = dR["calculateHistory"]
                                local g9 = g8[#g8]["pos"]
                                local ga = g8[#g8 - 1]["pos"]
                                local gb = g8[#g8]["time"] - g8[#g8 - 1]["time"]
                                if ((713 <= 847) and (gb > 0)) then
                                    local h2 = (g9 - ga) / gb
                                    if dR["calculateVelFilter"] then
                                        h2 = dR["calculateVelFilter"]
                                    end
                                    ey = h0 + (h2 * h1)
                                else
                                    ey = h0
                                end
                            end
                        end
                    end
                    if (dR["mode"] == "Random") then
                        local fd = (f1() - 0.5) * 2 * dR["radiusX"]
                        local fe = (f1() - 0.5) * 2 * dR["radiusY"]
                        local ff = (f1() - 0.5) * 2 * dR["radiusZ"]
                        if dR["useMinDistance"] then
                            if ((fd > 0) and (fd < dR["minDistanceX"])) then
                                fd = dR["minDistanceX"]
                            elseif ((2154 <= 4031) and (fd < 0) and (fd > -dR["minDistanceX"])) then
                                fd = -dR["minDistanceX"]
                            end
                            if ((fe > 0) and (fe < dR["minDistanceY"])) then
                                fe = dR["minDistanceY"]
                            elseif ((4615 == 4615) and (fe < 0) and (fe > -dR["minDistanceY"])) then
                                fe = -dR["minDistanceY"]
                            end
                            if (((ff > 0) and (ff < dR["minDistanceZ"])) or (3790 == 500)) then
                                ff = dR["minDistanceZ"]
                            elseif ((ff < 0) and (ff > -dR["minDistanceZ"])) then
                                ff = -dR["minDistanceZ"]
                            end
                        end
                        local h3 = dL.v3(ey["X"] + fd, ey["Y"] + fe, ey["Z"] + ff)
                        dL["desync"]:moveTo(h3.X, h3.Y, h3.Z)
                    elseif ((89 < 221) and (dR["mode"] == "Spiral")) then
                        dR["spiralAngle"] = dR["spiralAngle"] + (dR["spiralSpeed"] * gr * 4)
                        if ((2054 >= 1421) and (dR["spiralAngle"] >= 360)) then
                            dR["spiralAngle"] = dR["spiralAngle"] - 360
                        end
                        local gJ = math.rad(dR.spiralAngle)
                        local fd = g0(gJ) * dR["spiralDistance"]
                        local ff = f_(gJ) * dR["spiralDistance"]
                        local fe = dR["spiralYOffset"]
                        local h4 = dL.v3(ey["X"] + fd, ey["Y"] + fe, ey["Z"] + ff)
                        dL["desync"]:moveTo(h4.X, h4.Y, h4.Z)
                    elseif (dR["mode"] == "SpiralYZ") then
                        dR["spiralYZAngle"] = dR["spiralYZAngle"] + (dR["spiralYZSpeed"] * gr * 4)
                        if (dR["spiralYZAngle"] < 360) then
                        else
                            dR["spiralYZAngle"] = dR["spiralYZAngle"] - 360
                        end
                        local gJ = math.rad(dR.spiralYZAngle)
                        local fd = dR["spiralYZXOffset"]
                        local fe = g0(gJ) * dR["spiralYZDistance"]
                        local ff = f_(gJ) * dR["spiralYZDistance"]
                        local h5 = dL.v3(ey["X"] + fd, ey["Y"] + fe, ey["Z"] + ff)
                        dL["desync"]:moveTo(h5.X, h5.Y, h5.Z)
                    elseif ((692 < 3058) and (dR["mode"] == "SpiralYX")) then
                        dR["spiralYXAngle"] = dR["spiralYXAngle"] + (dR["spiralYXSpeed"] * gr * 4)
                        if ((dR["spiralYXAngle"] >= 360) or (3254 == 1655)) then
                            dR["spiralYXAngle"] = dR["spiralYXAngle"] - 360
                        end
                        local gJ = math.rad(dR.spiralYXAngle)
                        local fd = g0(gJ) * dR["spiralYXDistance"]
                        local fe = f_(gJ) * dR["spiralYXDistance"]
                        local ff = dR["spiralYXZOffset"]
                        local h6 = dL.v3(ey["X"] + fd, ey["Y"] + fe, ey["Z"] + ff)
                        dL["desync"]:moveTo(h6.X, h6.Y, h6.Z)
                    elseif ((dR["mode"] == "BaitSpiral") or (1296 == 4910)) then
                        local fh = tick()
                        if ((3368 == 3368) and dR["isBaiting"]) then
                            if ((2643 < 3815) and ((fh - dR["baitWaitStartTime"]) >= dR["baitWait"])) then
                                dR["isBaiting"] = false
                            else
                                if ((1913 > 493) and dR["baitTargetPos"]) then
                                    dL["desync"]:moveTo(
                                        dR["baitTargetPos"].X,
                                        dR["baitTargetPos"].Y,
                                        dR["baitTargetPos"].Z
                                    )
                                end
                                return
                            end
                        end
                        if (not dR["isBaiting"] and ((fh - dR["lastBaitTime"]) >= dR["baitCooldown"])) then
                            local gJ = math.rad(dR.baitSpiralAngle)
                            local h7 = g0(gJ) * dR["baitSpiralDistance"]
                            local h8 = f_(gJ) * dR["baitSpiralDistance"]
                            local gG = dL.v3(ey["X"] + h7, ey["Y"] + dR["baitSpiralYOffset"], ey["Z"] + h8)
                            dR["baitTargetPos"] = gF(ey, gG)
                            dL["desync"]:moveTo(dR["baitTargetPos"].X, dR["baitTargetPos"].Y, dR["baitTargetPos"].Z)
                            dR["isBaiting"] = true
                            dR["baitWaitStartTime"] = fh
                            dR["lastBaitTime"] = fh
                            return
                        end
                        dR["baitSpiralAngle"] = dR["baitSpiralAngle"] + (dR["baitSpiralSpeed"] * gr * 4)
                        if ((4755 > 3428) and (dR["baitSpiralAngle"] >= 360)) then
                            dR["baitSpiralAngle"] = dR["baitSpiralAngle"] - 360
                        end
                        local gJ = math.rad(dR.baitSpiralAngle)
                        local fd = g0(gJ) * dR["baitSpiralDistance"]
                        local ff = f_(gJ) * dR["baitSpiralDistance"]
                        local fe = dR["baitSpiralYOffset"]
                        local h9 = dL.v3(ey["X"] + fd, ey["Y"] + fe, ey["Z"] + ff)
                        dL["desync"]:moveTo(h9.X, h9.Y, h9.Z)
                    end
                end
                local function e1()
                    if ((1381 <= 2369) and dR["conn"]) then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function(gr)
                                    gR(gr)
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if dR["conn"] then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    dL["desync"]:syncWithPlayer()
                    dR["lastTarget"] = nil
                    dR["wasActive"] = false
                    dR["lastTargetLostTime"] = 0
                    dR["lastSyncTime"] = 0
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if eY then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setMode = function(self, eG)
                dR["mode"] = eG
            end
            f0.setRadiusX = function(self, d)
                dR["radiusX"] = d
            end
            f0.setRadiusY = function(self, d)
                dR["radiusY"] = d
            end
            f0.setRadiusZ = function(self, d)
                dR["radiusZ"] = d
            end
            f0.setUseMinDistance = function(self, d)
                dR["useMinDistance"] = d
            end
            f0.setMinDistanceX = function(self, d)
                dR["minDistanceX"] = d
            end
            f0.setMinDistanceY = function(self, d)
                dR["minDistanceY"] = d
            end
            f0.setMinDistanceZ = function(self, d)
                dR["minDistanceZ"] = d
            end
            f0.setSpiralDistance = function(self, d)
                dR["spiralDistance"] = d
            end
            f0.setSpiralSpeed = function(self, d)
                dR["spiralSpeed"] = d
            end
            f0.setSpiralYOffset = function(self, d)
                dR["spiralYOffset"] = d
            end
            f0.setSpiralYZDistance = function(self, d)
                dR["spiralYZDistance"] = d
            end
            f0.setSpiralYZSpeed = function(self, d)
                dR["spiralYZSpeed"] = d
            end
            f0.setSpiralYZXOffset = function(self, d)
                dR["spiralYZXOffset"] = d
            end
            f0.setSpiralYXDistance = function(self, d)
                dR["spiralYXDistance"] = d
            end
            f0.setSpiralYXSpeed = function(self, d)
                dR["spiralYXSpeed"] = d
            end
            f0.setSpiralYXZOffset = function(self, d)
                dR["spiralYXZOffset"] = d
            end
            f0.setBaitSpiralDistance = function(self, d)
                dR["baitSpiralDistance"] = d
            end
            f0.setBaitSpiralSpeed = function(self, d)
                dR["baitSpiralSpeed"] = d
            end
            f0.setBaitSpiralYOffset = function(self, d)
                dR["baitSpiralYOffset"] = d
            end
            f0.setBaitCooldown = function(self, d)
                dR["baitCooldown"] = d
            end
            f0.setBaitDistance = function(self, d)
                dR["baitDistance"] = d
            end
            f0.setBaitDirections = function(self, ha)
                dR["baitDirections"] = ha or {}
            end
            f0.setBaitWait = function(self, d)
                dR["baitWait"] = d
            end
            f0.setPredictEnable = function(self, eY)
                dR["predictEnable"] = eY
                if not eY then
                    dR["lastTargetPosition"] = nil
                    dR["lastTargetTime"] = nil
                    dR["resolveData"]["samples"] = {}
                end
            end
            f0.setPredictMode = function(self, eG)
                dR["predictMode"] = eG
                if ((eG == "Calculate") or (4843 == 4084)) then
                    dR["calculateHistory"] = {}
                    dR["calculateBias"] = dL.v3(0, 0, 0)
                    dR["calculateVelWeight"] = 1
                    dR["calculateVelFilter"] = nil
                    dR["calculateCorrect"] = 0
                    dR["calculateTotal"] = 0
                elseif (eG == "Regular") then
                    dR["lastTargetPosition"] = nil
                    dR["lastTargetTime"] = nil
                elseif (eG ~= "Better") then
                else
                    dR["betterPoseHistory"] = {}
                end
            end
            f0.setPredictStrength = function(self, d)
                dR["predictStrength"] = d
            end
            f0.setResolveEnable = function(self, eY)
                dR["resolveEnable"] = eY
                if ((4669 > 363) and eY) then
                    dR["resolveData"]["samples"] = {}
                end
            end
            f0.setResolveAggression = function(self, d)
                dR["resolveAggression"] = d
            end
            f0.setCalculateHistorySize = function(self, d)
                dR["calculateHistorySize"] = d
                while #dR["calculateHistory"] > d do
                    dL.remove(dR.calculateHistory, 1)
                end
            end
            f0.setCalculateVelWeight = function(self, d)
                dR["calculateVelWeight"] = d
            end
            f0.setCalculateAccWeight = function(self, d)
                dR["calculateAccWeight"] = d
            end
            f0.setCalculateAdaptRate = function(self, d)
                dR["calculateAdaptRate"] = d
            end
            f0.setBetterPingDivisionFactor = function(self, d)
                dR["betterPingDivisionFactor"] = d
            end
            f0.setAutoBuyModule = function(self, hb)
                dR["autoBuyModule"] = hb
            end
            f0.setAutoStompModule = function(self, hc)
                dR["autoStompModule"] = hc
            end
            f0.isCSyncActive = function(self)
                return dR["Enable"] and (ed["target"] ~= nil) and not f0:shouldStopCSync()
            end
            f0.canContinueDesync = function(self)
                return fO() and fR()
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_DesyncVisualise = function()
        return function(dL)
            local hd = {}
            local dN, eh, dP = dL["lp"], dL["camera"], dL["rnd"]
            local eg, ef = dL["userinput"], dL["workspace"]
            local ej, f2, he, hf = dL["v2"], dL["v3"], dL["c3rgb"], dL["new"]
            local dQ = dL["cf"]
            local hg = dL["draw"]
            local dR = {
                Enable = false,
                tracerEnable = false,
                dummyEnable = false,
                imageEnable = false,
                dummyType = "R6",
                dummyColor = he(255, 255, 255),
                dummyTransparency = 0.7,
                imageColor = he(255, 255, 255),
                imageTransparency = 0.7,
                imageScale = 1,
                conn = nil,
                desyncApi = nil,
                dummyModel = nil,
                clonePartMap = {},
                imageAttachPart = nil,
                imageCircle = nil
            }
            local hh = {}
            do
                hh["outline"] = hg.new("Line")
                hh["outline"]["Visible"] = false
                hh["outline"]["Color"] = he(0, 0, 0)
                hh["outline"]["Thickness"] = 3
                hh["outline"]["Transparency"] = 1
                hh["main"] = hg.new("Line")
                hh["main"]["Visible"] = false
                hh["main"]["Color"] = he(255, 255, 255)
                hh["main"]["Thickness"] = 1.5
                hh["main"]["Transparency"] = 1
            end
            do
                hd.getRoot = function(self)
                    local dS = dN["Character"]
                    if (not dS or (1877 >= 3138)) then
                        return nil
                    end
                    local dT = dS:FindFirstChildOfClass("Humanoid")
                    return dT and dT["RootPart"]
                end
                hd.getPosition = function(self)
                    if ((4742 >= 3626) and dR["desyncApi"] and dR["desyncApi"]:isEnable()) then
                        return dR["desyncApi"]:getPosition()
                    end
                    local e0 = self:getRoot()
                    return e0 and e0["Position"]
                end
            end
            do
                local function hi()
                    if not dR["tracerEnable"] then
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                        return
                    end
                    local en = hd:getPosition()
                    if not en then
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                        return
                    end
                    local ew, eo = eh:WorldToViewportPoint(en)
                    if ((eo and (ew["Z"] > 0)) or (4540 == 916)) then
                        local ex = eg:GetMouseLocation()
                        local hj = ej(ew.X, ew.Y)
                        hh["outline"]["From"] = ex
                        hh["outline"]["To"] = hj
                        hh["outline"]["Visible"] = true
                        hh["main"]["From"] = ex
                        hh["main"]["To"] = hj
                        hh["main"]["Visible"] = true
                    else
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                    end
                end
                hd["updateTracer"] = hi
            end
            do
                local function hk()
                    local hl = hf("Model")
                    hl["Name"] = "DesyncDummy"
                    hl["Parent"] = ef
                    local hm = {
                        {Name = "Head", Size = f2(2, 1, 1)},
                        {Name = "Torso", Size = f2(2, 2, 1)},
                        {Name = "Left Arm", Size = f2(1, 2, 1)},
                        {Name = "Right Arm", Size = f2(1, 2, 1)},
                        {Name = "Left Leg", Size = f2(1, 2, 1)},
                        {Name = "Right Leg", Size = f2(1, 2, 1)}
                    }
                    for D, hn in pairs(hm) do
                        local ho = hf("Part")
                        ho["Name"] = hn["Name"]
                        ho["Size"] = hn["Size"]
                        ho["Material"] = Enum["Material"]["Neon"]
                        ho["Color"] = he(255, 255, 255)
                        ho["Transparency"] = 0.7
                        ho["CanCollide"] = false
                        ho["Anchored"] = true
                        ho["CastShadow"] = false
                        ho["TopSurface"] = Enum["SurfaceType"]["Smooth"]
                        ho["BottomSurface"] = Enum["SurfaceType"]["Smooth"]
                        ho["Parent"] = hl
                    end
                    return hl
                end
                local function hp()
                    local dS = dN["Character"]
                    if not dS then
                        return nil
                    end
                    local hl = hf("Model")
                    hl["Name"] = "DesyncClone"
                    dR["clonePartMap"] = {}
                    local hq = {
                        "Head",
                        "UpperTorso",
                        "LowerTorso",
                        "LeftUpperArm",
                        "LeftLowerArm",
                        "LeftHand",
                        "RightUpperArm",
                        "RightLowerArm",
                        "RightHand",
                        "LeftUpperLeg",
                        "LeftLowerLeg",
                        "LeftFoot",
                        "RightUpperLeg",
                        "RightLowerLeg",
                        "RightFoot"
                    }
                    for D, eU in pairs(hq) do
                        local hr = dS:FindFirstChild(eU)
                        if ((hr and hr:IsA("BasePart")) or (1156 > 4345)) then
                            local hs = hr:Clone()
                            for D, ht in pairs(hs:GetDescendants()) do
                                if ((2237 < 4249) and (ht:IsA("Motor6D") or ht:IsA("Weld") or ht:IsA("Attachment"))) then
                                    ht:Destroy()
                                end
                            end
                            if ((hs["Name"] == "Head") and hs:IsA("MeshPart")) then
                                hs["TextureID"] = ""
                            end
                            hs["Material"] = Enum["Material"]["Neon"]
                            hs["CanCollide"] = false
                            hs["Anchored"] = true
                            hs["CastShadow"] = false
                            hs["Parent"] = hl
                            dR["clonePartMap"][hs] = hr
                        end
                    end
                    hl["Parent"] = ef
                    return hl
                end
                local function hu()
                    if (dR["dummyModel"] or (2683 < 23)) then
                        dR["dummyModel"]:Destroy()
                        dR["clonePartMap"] = {}
                    end
                    if (dR["dummyType"] == "R6") then
                        dR["dummyModel"] = hk()
                    elseif ((697 <= 826) and (dR["dummyType"] == "Clone")) then
                        dR["dummyModel"] = hp()
                    end
                    if dR["dummyModel"] then
                        for D, ho in pairs(dR["dummyModel"]:GetChildren()) do
                            if ho:IsA("BasePart") then
                                ho["Color"] = dR["dummyColor"]
                                ho["Transparency"] = dR["dummyTransparency"]
                            end
                        end
                    end
                end
                local function hv()
                    if dR["dummyModel"] then
                        dR["dummyModel"]:Destroy()
                        dR["dummyModel"] = nil
                        dR["clonePartMap"] = {}
                    end
                end
                local function hw()
                    if ((1105 <= 1176) and not dR["dummyEnable"]) then
                        hv()
                        return
                    end
                    local dS = dN["Character"]
                    local dT = dS and dS:FindFirstChildOfClass("Humanoid")
                    local hx = dS and dS:FindFirstChild("FULLY_LOADED_CHAR")
                    if (not dS or not hx or not dT or (dT["Health"] <= 0)) then
                        hv()
                        return
                    end
                    local en = hd:getPosition()
                    if not en then
                        if dR["dummyModel"] then
                            for D, ho in pairs(dR["dummyModel"]:GetDescendants()) do
                                if ((3379 <= 3812) and ho:IsA("BasePart")) then
                                    ho["Transparency"] = 1
                                end
                            end
                        end
                        return
                    end
                    if not dR["dummyModel"] then
                        hu()
                        if not dR["dummyModel"] then
                            return
                        end
                    end
                    if ((dR["dummyType"] == "R6") or (788 >= 1616)) then
                        local e0 = hd:getRoot()
                        local hy = (e0 and e0["CFrame"]) or dQ(0, 0, 0)
                        local hz = dQ(en) * (hy - hy["Position"])
                        local hA = dR["dummyModel"]:FindFirstChild("Torso")
                        local fE = dR["dummyModel"]:FindFirstChild("Head")
                        local hB = dR["dummyModel"]:FindFirstChild("Left Arm")
                        local hC = dR["dummyModel"]:FindFirstChild("Right Arm")
                        local hD = dR["dummyModel"]:FindFirstChild("Left Leg")
                        local hE = dR["dummyModel"]:FindFirstChild("Right Leg")
                        if hA then
                            hA["CFrame"] = hz
                        end
                        if ((1854 <= 3379) and fE) then
                            fE["CFrame"] = hz * dQ(0, 1.5, 0)
                        end
                        if hB then
                            hB["CFrame"] = hz * dQ(-1.5, 0, 0)
                        end
                        if ((4549 == 4549) and hC) then
                            hC["CFrame"] = hz * dQ(1.5, 0, 0)
                        end
                        if hD then
                            hD["CFrame"] = hz * dQ(-0.5, -2, 0)
                        end
                        if (hE or (3022 >= 3024)) then
                            hE["CFrame"] = hz * dQ(0.5, -2, 0)
                        end
                    elseif (dR["dummyType"] == "Clone") then
                        local e0 = hd:getRoot()
                        if ((4820 > 2198) and not e0) then
                            return
                        end
                        for hs, hr in pairs(dR.clonePartMap) do
                            if (not hr or not hr["Parent"] or (1061 >= 4891)) then
                                hv()
                                hu()
                                return
                            end
                        end
                        local hF = en - e0["Position"]
                        for hs, hr in pairs(dR.clonePartMap) do
                            hs["CFrame"] = hr["CFrame"] + hF
                            hs["CanCollide"] = false
                        end
                    end
                end
                hd["updateDummy"] = hw
                hd["createDummy"] = hu
                hd["destroyDummy"] = hv
            end
            do
                local function hG()
                    if ((1364 <= 4473) and dR["imageAttachPart"]) then
                        dR["imageAttachPart"]:Destroy()
                    end
                    local hH = hf("Part")
                    hH["Name"] = "DesyncImageAttachment"
                    hH["Size"] = f2(0.1, 0.1, 0.1)
                    hH["Transparency"] = 1
                    hH["CanCollide"] = false
                    hH["Anchored"] = true
                    hH["CastShadow"] = false
                    hH["Parent"] = ef
                    local hI = hf("BillboardGui")
                    hI["Name"] = "DesyncImageIndicator"
                    hI["Adornee"] = hH
                    hI["Size"] = UDim2.new(0, 60 * dR["imageScale"], 0, 60 * dR["imageScale"])
                    hI["AlwaysOnTop"] = true
                    hI["Parent"] = hH
                    local hJ = hf("ImageLabel")
                    hJ["Name"] = "DesyncCircle"
                    hJ["Size"] = UDim2.new(1, 0, 1, 0)
                    hJ["AnchorPoint"] = ej(0.5, 0.5)
                    hJ["Position"] = UDim2.new(0.5, 0, 0.5, 0)
                    hJ["BackgroundTransparency"] = 1
                    hJ["Image"] = "rbxassetid://139422593360273"
                    hJ["ImageColor3"] = dR["imageColor"]
                    hJ["ImageTransparency"] = dR["imageTransparency"]
                    hJ["ZIndex"] = 9
                    hJ["Parent"] = hI
                    dR["imageAttachPart"] = hH
                    dR["imageCircle"] = hJ
                end
                local function hK()
                    if (not dR["imageEnable"] or (3595 <= 3)) then
                        if (dR["imageAttachPart"] or (4672 == 3852)) then
                            dR["imageAttachPart"]["Parent"] = nil
                        end
                        return
                    end
                    local en = hd:getPosition()
                    if not en then
                        if ((1559 == 1559) and dR["imageAttachPart"]) then
                            dR["imageAttachPart"]["Parent"] = nil
                        end
                        return
                    end
                    if (not dR["imageAttachPart"] or not dR["imageCircle"] or (1752 <= 788)) then
                        hG()
                    end
                    if (dR["imageAttachPart"] or (3907 == 177)) then
                        dR["imageAttachPart"]["CFrame"] = dQ(en)
                        dR["imageAttachPart"]["Parent"] = ef
                    end
                end
                local function hL()
                    if ((3470 > 555) and dR["imageAttachPart"]) then
                        dR["imageAttachPart"]:Destroy()
                        dR["imageAttachPart"] = nil
                        dR["imageCircle"] = nil
                    end
                end
                hd["updateImage"] = hK
                hd["createImage"] = hG
                hd["destroyImage"] = hL
            end
            do
                local function e1()
                    if (dR["conn"] or (972 == 645)) then
                        return
                    end
                    dR["conn"] =
                        dP:Connect(
                        (
                            newcclosure(
                                function()
                                    if ((3182 >= 2115) and not dR["Enable"]) then
                                        return
                                    end
                                    if ((3893 < 4429) and dR["tracerEnable"]) then
                                        hd:updateTracer()
                                    end
                                    if dR["dummyEnable"] then
                                        hd:updateDummy()
                                    end
                                    if (dR["imageEnable"] or (2867 < 1905)) then
                                        hd:updateImage()
                                    end
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if dR["conn"] then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    hh["outline"]["Visible"] = false
                    hh["main"]["Visible"] = false
                    if dR["dummyModel"] then
                        dR["dummyModel"]:Destroy()
                        dR["dummyModel"] = nil
                    end
                    if (dR["imageAttachPart"] or (1796 >= 4051)) then
                        dR["imageAttachPart"]:Destroy()
                        dR["imageAttachPart"] = nil
                        dR["imageCircle"] = nil
                    end
                end
                hd["startLoop"] = e1
                hd["stopLoop"] = e3
            end
            hd.setDesyncApi = function(self, hM)
                dR["desyncApi"] = hM
            end
            local function hN()
                local hO = dR["tracerEnable"] or dR["dummyEnable"] or dR["imageEnable"]
                if ((1619 <= 3756) and hO and not dR["Enable"]) then
                    dR["Enable"] = true
                    hd:startLoop()
                elseif ((604 == 604) and not hO and dR["Enable"]) then
                    dR["Enable"] = false
                    hd:stopLoop()
                end
            end
            hd.setTracerEnable = function(self, eY)
                dR["tracerEnable"] = eY
                if not eY then
                    hh["outline"]["Visible"] = false
                    hh["main"]["Visible"] = false
                end
                hN()
            end
            hd.setDummyEnable = function(self, eY)
                dR["dummyEnable"] = eY
                if (eY or (4484 == 900)) then
                    hd:createDummy()
                else
                    hd:destroyDummy()
                end
                hN()
            end
            hd.setImageEnable = function(self, eY)
                dR["imageEnable"] = eY
                if eY then
                    hd:createImage()
                else
                    hd:destroyImage()
                end
                hN()
            end
            hd.setOutlineColor = function(self, hP, hQ)
                hh["outline"]["Color"] = hP
                hh["outline"]["Transparency"] = 1 - hQ
            end
            hd.setMainColor = function(self, hP, hQ)
                hh["main"]["Color"] = hP
                hh["main"]["Transparency"] = 1 - hQ
            end
            hd.setDummyType = function(self, hR)
                dR["dummyType"] = hR
                if dR["dummyEnable"] then
                    self:destroyDummy()
                    self:createDummy()
                end
            end
            hd.setDummyColor = function(self, hP, hQ)
                dR["dummyColor"] = hP
                dR["dummyTransparency"] = hQ
                if dR["dummyModel"] then
                    for D, ho in pairs(dR["dummyModel"]:GetChildren()) do
                        if (ho:IsA("BasePart") or (4459 <= 1113)) then
                            ho["Color"] = hP
                            ho["Transparency"] = hQ
                        end
                    end
                end
            end
            hd.setImageColor = function(self, hP, hQ)
                dR["imageColor"] = hP
                dR["imageTransparency"] = hQ
                if dR["imageCircle"] then
                    dR["imageCircle"]["ImageColor3"] = hP
                    dR["imageCircle"]["ImageTransparency"] = hQ
                end
            end
            hd.setImageScale = function(self, hS)
                dR["imageScale"] = hS
                if ((3632 > 3398) and dR["imageAttachPart"]) then
                    local hI = dR["imageAttachPart"]:FindFirstChild("DesyncImageIndicator")
                    if ((4082 <= 4917) and hI) then
                        hI["Size"] = UDim2.new(0, 60 * hS, 0, 60 * hS)
                    end
                end
            end
            hd.init = function(self)
            end
            return hd
        end
    end,
    Ragebot_DesyncVoidHide = function()
        return function(dL)
            local f0 = {}
            local dO, fo, wait = dL["heart"], dL["spawn"], dL["wait"]
            local f1, ei, hT = dL["random"], dL["huge"], dL["min"]
            local ek = dL["insert"]
            local dR = {
                Enable = false,
                pattern = "Deep Void",
                deepDirection = "-Y",
                deepSwitchSpeed = 0.05,
                depthMultiplier = 1,
                breakDirection = "-Y",
                breakSwitchSpeed = 0.05,
                conn = nil,
                deepVoidPositions = {},
                breakNullPositions = {},
                currentDeepVoidIndex = 1,
                currentBreakNullIndex = 1,
                lastDeepVoidSwitch = 0,
                lastBreakNullSwitch = 0,
                autoBuyModule = nil,
                voidReloadModule = nil,
                autoStompModule = nil,
                csyncModule = nil
            }
            do
                f0.generateDeepVoidPositions = function(self)
                    local hU = {}
                    local hV = {-2000000, -5000000, -10000000, -20000000, -50000000}
                    local hW = {-1000000, -500000, -250000, -100000, 100000, 250000, 500000, 1000000}
                    for w = 1, 20 do
                        local hX, hY, hZ
                        if (dR["deepDirection"] == "+Y") then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = -hV[f1(1, #hV)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((4832 >= 1386) and (dR["deepDirection"] == "-Y")) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hV[f1(1, #hV)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((137 == 137) and (dR["deepDirection"] == "+Z")) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = -hV[f1(1, #hV)] + f1(-10000, 10000)
                        elseif ((dR["deepDirection"] == "-Z") or (1570 >= 4332)) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hV[f1(1, #hV)] + f1(-10000, 10000)
                        elseif ((dR["deepDirection"] == "+X") or (4064 <= 1819)) then
                            hX = -hV[f1(1, #hV)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((dR["deepDirection"] == "-X") or (4986 < 1574)) then
                            hX = hV[f1(1, #hV)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        end
                        ek(hU, {x = hX, y = hY, z = hZ})
                    end
                    if (dR["deepDirection"] == "+Y") then
                        ek(hU, {x = 0, y = 5000000, z = 0})
                        ek(hU, {x = 750000, y = 7500000, z = 750000})
                        ek(hU, {x = -750000, y = 7500000, z = -750000})
                    elseif ((4426 > 172) and (dR["deepDirection"] == "-Y")) then
                        ek(hU, {x = 0, y = -5000000, z = 0})
                        ek(hU, {x = 750000, y = -7500000, z = 750000})
                        ek(hU, {x = -750000, y = -7500000, z = -750000})
                    elseif (dR["deepDirection"] == "+Z") then
                        ek(hU, {x = 0, y = 0, z = 5000000})
                        ek(hU, {x = 750000, y = 750000, z = 7500000})
                        ek(hU, {x = -750000, y = -750000, z = 7500000})
                    elseif (dR["deepDirection"] == "-Z") then
                        ek(hU, {x = 0, y = 0, z = -5000000})
                        ek(hU, {x = 750000, y = 750000, z = -7500000})
                        ek(hU, {x = -750000, y = -750000, z = -7500000})
                    elseif (dR["deepDirection"] == "+X") then
                        ek(hU, {x = 5000000, y = 0, z = 0})
                        ek(hU, {x = 7500000, y = 750000, z = 750000})
                        ek(hU, {x = 7500000, y = -750000, z = -750000})
                    elseif (dR["deepDirection"] ~= "-X") then
                    else
                        ek(hU, {x = -5000000, y = 0, z = 0})
                        ek(hU, {x = -7500000, y = 750000, z = 750000})
                        ek(hU, {x = -7500000, y = -750000, z = -750000})
                    end
                    return hU
                end
                f0.generateBreakNullPositions = function(self)
                    local hU = {}
                    local h_ = 10000000272564224
                    local hW = {-100000000, -50000000, -25000000, -10000000, 10000000, 25000000, 50000000, 100000000}
                    for w = 1, 20 do
                        local hX, hY, hZ
                        if ((586 > 455) and (dR["breakDirection"] == "+Y")) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = h_
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif (dR["breakDirection"] == "-Y") then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = -h_
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((826 == 826) and (dR["breakDirection"] == "+Z")) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = h_
                        elseif (dR["breakDirection"] == "-Z") then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = -h_
                        elseif (dR["breakDirection"] == "+X") then
                            hX = h_
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif (dR["breakDirection"] ~= "-X") then
                        else
                            hX = -h_
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        end
                        ek(hU, {x = hX, y = hY, z = hZ})
                    end
                    if (dR["breakDirection"] == "+Y") then
                        ek(hU, {x = 0, y = 10000000272564224, z = 0})
                        ek(hU, {x = 75000000, y = 10000000272564224, z = 75000000})
                        ek(hU, {x = -75000000, y = 10000000272564224, z = -75000000})
                    elseif (dR["breakDirection"] == "-Y") then
                        ek(hU, {x = 0, y = -10000000272564224, z = 0})
                        ek(hU, {x = 75000000, y = -10000000272564224, z = 75000000})
                        ek(hU, {x = -75000000, y = -10000000272564224, z = -75000000})
                    elseif ((dR["breakDirection"] == "+Z") or (4019 > 4441)) then
                        ek(hU, {x = 0, y = 0, z = 10000000272564224})
                        ek(hU, {x = 75000000, y = 75000000, z = 10000000272564224})
                        ek(hU, {x = -75000000, y = -75000000, z = 10000000272564224})
                    elseif (dR["breakDirection"] == "-Z") then
                        ek(hU, {x = 0, y = 0, z = -10000000272564224})
                        ek(hU, {x = 75000000, y = 75000000, z = -10000000272564224})
                        ek(hU, {x = -75000000, y = -75000000, z = -10000000272564224})
                    elseif ((2017 < 4261) and (dR["breakDirection"] == "+X")) then
                        ek(hU, {x = 10000000272564224, y = 0, z = 0})
                        ek(hU, {x = 10000000272564224, y = 75000000, z = 75000000})
                        ek(hU, {x = 10000000272564224, y = -75000000, z = -75000000})
                    elseif ((4716 > 80) and (dR["breakDirection"] == "-X")) then
                        ek(hU, {x = -10000000272564224, y = 0, z = 0})
                        ek(hU, {x = -10000000272564224, y = 75000000, z = 75000000})
                        ek(hU, {x = -10000000272564224, y = -75000000, z = -75000000})
                    end
                    return hU
                end
            end
            do
                local function i0()
                    if not dR["Enable"] then
                        return
                    end
                    if ((dR["autoBuyModule"] and dR["autoBuyModule"]:isBuyingInProgress()) or (3507 == 3272)) then
                        return
                    end
                    if ((dR["voidReloadModule"] and dR["voidReloadModule"]:shouldGoToVoid()) or (876 >= 3075)) then
                        return
                    end
                    if dR["autoStompModule"] then
                        if dR["autoStompModule"]:isStompingInProgress() then
                            return
                        end
                        if not dR["autoStompModule"]:canContinueDesync() then
                            return
                        end
                    end
                    if ((4352 > 2554) and dR["csyncModule"]) then
                        if (dR["csyncModule"]:isCSyncActive() or (4406 < 4043)) then
                            return
                        end
                        if not dR["csyncModule"]:canContinueDesync() then
                            return
                        end
                    end
                    if ((dR["pattern"] == "Deep Void") or (1889 >= 3383)) then
                        local fh = tick()
                        if ((1892 <= 2734) and ((fh - dR["lastDeepVoidSwitch"]) < dR["deepSwitchSpeed"])) then
                            return
                        end
                        if (#dR["deepVoidPositions"] ~= 0) then
                        else
                            dR["deepVoidPositions"] = f0:generateDeepVoidPositions()
                        end
                        dR["currentDeepVoidIndex"] = (dR["currentDeepVoidIndex"] % #dR["deepVoidPositions"]) + 1
                        local i1 = dR["deepVoidPositions"][dR["currentDeepVoidIndex"]]
                        local hX = i1["x"] * hT(dR.depthMultiplier, 50)
                        local hY = i1["y"] * dR["depthMultiplier"]
                        local hZ = i1["z"] * hT(dR.depthMultiplier, 50)
                        dR["lastDeepVoidSwitch"] = fh
                        dL["desync"]:moveTo(hX, hY, hZ)
                    elseif (dR["pattern"] ~= "Break Null") then
                    else
                        local fh = tick()
                        if ((fh - dR["lastBreakNullSwitch"]) >= dR["breakSwitchSpeed"]) then
                        else
                            return
                        end
                        if (#dR["breakNullPositions"] ~= 0) then
                        else
                            dR["breakNullPositions"] = f0:generateBreakNullPositions()
                        end
                        dR["currentBreakNullIndex"] = (dR["currentBreakNullIndex"] % #dR["breakNullPositions"]) + 1
                        local i1 = dR["breakNullPositions"][dR["currentBreakNullIndex"]]
                        dR["lastBreakNullSwitch"] = fh
                        dL["desync"]:moveTo(i1.x, i1.y, i1.z)
                    end
                end
                local function e1()
                    if ((1923 < 2218) and dR["conn"]) then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function()
                                    i0()
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if ((2173 > 379) and dR["conn"]) then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    dL["desync"]:syncWithPlayer()
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if (eY or (2591 == 3409)) then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setPattern = function(self, i2)
                dR["pattern"] = i2
                if (i2 == "Deep Void") then
                    dR["deepVoidPositions"] = self:generateDeepVoidPositions()
                    dR["currentDeepVoidIndex"] = 1
                    dR["lastDeepVoidSwitch"] = 0
                elseif (i2 == "Break Null") then
                    dR["breakNullPositions"] = self:generateBreakNullPositions()
                    dR["currentBreakNullIndex"] = 1
                    dR["lastBreakNullSwitch"] = 0
                end
            end
            f0.setDeepDirection = function(self, g_)
                dR["deepDirection"] = g_
                dR["deepVoidPositions"] = self:generateDeepVoidPositions()
                dR["currentDeepVoidIndex"] = 1
                dR["lastDeepVoidSwitch"] = 0
            end
            f0.setDeepSwitchSpeed = function(self, i3)
                dR["deepSwitchSpeed"] = i3
            end
            f0.setDepthMultiplier = function(self, i4)
                dR["depthMultiplier"] = i4
            end
            f0.setBreakDirection = function(self, g_)
                dR["breakDirection"] = g_
                dR["breakNullPositions"] = self:generateBreakNullPositions()
                dR["currentBreakNullIndex"] = 1
                dR["lastBreakNullSwitch"] = 0
            end
            f0.setBreakSwitchSpeed = function(self, i3)
                dR["breakSwitchSpeed"] = i3
            end
            f0.setAutoBuyModule = function(self, hb)
                dR["autoBuyModule"] = hb
            end
            f0.setVoidReloadModule = function(self, i5)
                dR["voidReloadModule"] = i5
            end
            f0.setAutoStompModule = function(self, hc)
                dR["autoStompModule"] = hc
            end
            f0.setCSyncModule = function(self, i6)
                dR["csyncModule"] = i6
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_DesyncVoidReload = function()
        return function(dL)
            local f0 = {}
            local dN, dO = dL["lp"], dL["heart"]
            local f1, ek = dL["random"], dL["insert"]
            local i7 = dL["replicatedstorage"]
            local f3 = i7:WaitForChild("MainEvent")
            local dR = {
                Enable = false,
                breakDirection = "-Y",
                breakSwitchSpeed = 0.05,
                conn = nil,
                breakNullPositions = {},
                currentBreakNullIndex = 1,
                lastBreakNullSwitch = 0,
                autoBuyModule = nil
            }
            do
                f0.generateBreakNullPositions = function(self)
                    local hU = {}
                    local h_ = 10000000272564224
                    local hW = {-100000000, -50000000, -25000000, -10000000, 10000000, 25000000, 50000000, 100000000}
                    for w = 1, 20 do
                        local hX, hY, hZ
                        if ((4514 > 3324) and (dR["breakDirection"] == "+Y")) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = h_
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((dR["breakDirection"] == "-Y") or (208 >= 4828)) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = -h_
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((dR["breakDirection"] == "+Z") or (1583 > 3567)) then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = h_
                        elseif (dR["breakDirection"] == "-Z") then
                            hX = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = -h_
                        elseif ((dR["breakDirection"] == "+X") or (1313 == 794)) then
                            hX = h_
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        elseif ((3174 > 2902) and (dR["breakDirection"] == "-X")) then
                            hX = -h_
                            hY = hW[f1(1, #hW)] + f1(-10000, 10000)
                            hZ = hW[f1(1, #hW)] + f1(-10000, 10000)
                        end
                        ek(hU, {x = hX, y = hY, z = hZ})
                    end
                    if ((4120 <= 4260) and (dR["breakDirection"] == "+Y")) then
                        ek(hU, {x = 0, y = 10000000272564224, z = 0})
                        ek(hU, {x = 75000000, y = 10000000272564224, z = 75000000})
                        ek(hU, {x = -75000000, y = 10000000272564224, z = -75000000})
                    elseif (dR["breakDirection"] == "-Y") then
                        ek(hU, {x = 0, y = -10000000272564224, z = 0})
                        ek(hU, {x = 75000000, y = -10000000272564224, z = 75000000})
                        ek(hU, {x = -75000000, y = -10000000272564224, z = -75000000})
                    elseif ((dR["breakDirection"] == "+Z") or (883 > 4778)) then
                        ek(hU, {x = 0, y = 0, z = 10000000272564224})
                        ek(hU, {x = 75000000, y = 75000000, z = 10000000272564224})
                        ek(hU, {x = -75000000, y = -75000000, z = 10000000272564224})
                    elseif ((dR["breakDirection"] == "-Z") or (3620 >= 4891)) then
                        ek(hU, {x = 0, y = 0, z = -10000000272564224})
                        ek(hU, {x = 75000000, y = 75000000, z = -10000000272564224})
                        ek(hU, {x = -75000000, y = -75000000, z = -10000000272564224})
                    elseif (dR["breakDirection"] == "+X") then
                        ek(hU, {x = 10000000272564224, y = 0, z = 0})
                        ek(hU, {x = 10000000272564224, y = 75000000, z = 75000000})
                        ek(hU, {x = 10000000272564224, y = -75000000, z = -75000000})
                    elseif ((4258 > 937) and (dR["breakDirection"] == "-X")) then
                        ek(hU, {x = -10000000272564224, y = 0, z = 0})
                        ek(hU, {x = -10000000272564224, y = 75000000, z = 75000000})
                        ek(hU, {x = -10000000272564224, y = -75000000, z = -75000000})
                    end
                    return hU
                end
            end
            do
                local function i8()
                    if not dN["Character"] then
                        return false
                    end
                    local eD = dN["Character"]:FindFirstChild("BodyEffects")
                    if not eD then
                        return false
                    end
                    local i9 = eD:FindFirstChild("Reload")
                    if (not i9 or not i9:IsA("BoolValue")) then
                        return false
                    end
                    return i9["Value"] == true
                end
                local function ia()
                    if (not dN["Character"] or (4869 < 906)) then
                        return false
                    end
                    for D, fl in ipairs(dN["Character"]:GetChildren()) do
                        if (fl:IsA("Tool") and fl:FindFirstChild("Ammo")) then
                            if (fl["Ammo"]["Value"] > 0) then
                            else
                                return true
                            end
                        end
                    end
                    return false
                end
                local function ib()
                    if not dN["Character"] then
                        return
                    end
                    for D, fl in ipairs(dN["Character"]:GetChildren()) do
                        if (fl:IsA("Tool") and fl:FindFirstChild("Ammo")) then
                            if (fl["Ammo"]["Value"] <= 0) then
                                pcall(
                                    function()
                                        f3:FireServer("Reload", fl)
                                    end
                                )
                            end
                        end
                    end
                end
                f0.shouldGoToVoid = function(self)
                    if (not dR["Enable"] or (1225 > 4228)) then
                        return false
                    end
                    return i8() or ia()
                end
                f0.performReload = function(self)
                    ib()
                end
            end
            do
                local ic = false
                local function id()
                    if ((3328 > 2238) and not dR["Enable"]) then
                        return
                    end
                    if ((3839 > 1405) and dR["autoBuyModule"] and dR["autoBuyModule"]:isBuyingInProgress()) then
                        return
                    end
                    if (not f0:shouldGoToVoid() or (1293 <= 507)) then
                        if (ic or (2896 < 805)) then
                            dL["desync"]:syncWithPlayer()
                            ic = false
                        end
                        return
                    end
                    ic = true
                    local fh = tick()
                    if ((2316 == 2316) and ((fh - dR["lastBreakNullSwitch"]) < dR["breakSwitchSpeed"])) then
                        return
                    end
                    if ((#dR["breakNullPositions"] == 0) or (2570 == 1533)) then
                        dR["breakNullPositions"] = f0:generateBreakNullPositions()
                    end
                    dR["currentBreakNullIndex"] = (dR["currentBreakNullIndex"] % #dR["breakNullPositions"]) + 1
                    local i1 = dR["breakNullPositions"][dR["currentBreakNullIndex"]]
                    dR["lastBreakNullSwitch"] = fh
                    dL["desync"]:moveTo(i1.x, i1.y, i1.z)
                    f0:performReload()
                end
                local function e1()
                    if (dR["conn"] or (883 == 1460)) then
                        return
                    end
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function()
                                    id()
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if dR["conn"] then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    if (ic or (4619 <= 999)) then
                        dL["desync"]:syncWithPlayer()
                        ic = false
                    end
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if eY then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setBreakDirection = function(self, g_)
                dR["breakDirection"] = g_
                dR["breakNullPositions"] = self:generateBreakNullPositions()
                dR["currentBreakNullIndex"] = 1
                dR["lastBreakNullSwitch"] = 0
            end
            f0.setBreakSwitchSpeed = function(self, i3)
                dR["breakSwitchSpeed"] = i3
            end
            f0.setAutoBuyModule = function(self, hb)
                dR["autoBuyModule"] = hb
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_MultiGuns = function()
        return function(dL)
            local f0 = {}
            local dN, dO, ef = dL["lp"], dL["heart"], dL["workspace"]
            local fo, wait = dL["spawn"], dL["wait"]
            local ek, ie = dL["insert"], dL["remove"]
            local dR = {
                Enable = false,
                autoBuyModule = nil,
                conn = nil,
                charAddedConn = nil,
                toolAddedConn = nil,
                toolRemovedConn = nil,
                equippedTools = {},
                lastEquipTime = 0,
                lastReequipTime = 0,
                equipCooldown = 0.05,
                selectedGuns = {}
            }
            local ig = {
                ["[AUG]"] = true,
                ["[Rifle]"] = true,
                ["[LMG]"] = true,
                ["[P90]"] = true,
                ["[Flintlock]"] = true,
                ["[Revolver]"] = true,
                ["[Double-Barrel SG]"] = true,
                ["[AK47]"] = true,
                ["[TacticalShotgun]"] = true,
                ["[Shotgun]"] = true,
                ["[SMG]"] = true,
                ["[DrumGun]"] = true,
                ["[Glock]"] = true,
                ["[Silencer]"] = true,
                ["[AR]"] = true
            }
            local ih = {
                "Head",
                "UpperTorso",
                "LowerTorso",
                "LeftUpperArm",
                "LeftLowerArm",
                "LeftHand",
                "RightUpperArm",
                "RightLowerArm",
                "RightHand",
                "LeftUpperLeg",
                "LeftLowerLeg",
                "LeftFoot",
                "RightUpperLeg",
                "RightLowerLeg",
                "RightFoot"
            }
            do
                local function ii()
                    if not dN["Character"] then
                        return false
                    end
                    for D, eU in ipairs(ih) do
                        if (not dN["Character"]:FindFirstChild(eU) or (3410 > 4116)) then
                            return false
                        end
                    end
                    return true
                end
                local function ij()
                    if (not dN["Character"] or (903 >= 3059)) then
                        return false
                    end
                    local fu = ef:FindFirstChild("Players")
                    if (fu or (3976 < 2857)) then
                        local fv = fu:FindFirstChild(dN.Name)
                        if fv then
                            local ik = fv:FindFirstChild("FULLY_LOADED_CHAR")
                            if ik then
                                return true
                            end
                        end
                    end
                    return false
                end
                local function il()
                    if ((4930 > 2307) and not ii()) then
                        return
                    end
                    for w = #dR["equippedTools"], 1, -1 do
                        dR["equippedTools"][w] = nil
                    end
                    local fh = tick()
                    if (((fh - dR["lastEquipTime"]) < dR["equipCooldown"]) or (4046 < 1291)) then
                        return
                    end
                    dR["lastEquipTime"] = fh
                    local im = dN:FindFirstChild("Backpack")
                    if im then
                        for D, fl in ipairs(im:GetChildren()) do
                            if (fl:IsA("Tool") and ig[fl["Name"]]) then
                                local io = false
                                for D, ip in ipairs(dR.selectedGuns) do
                                    if (fl["Name"] ~= ip) then
                                    else
                                        io = true
                                        break
                                    end
                                end
                                if (io or (4241 == 3545)) then
                                    pcall(
                                        function()
                                            fl["Parent"] = dN["Character"]
                                            wait(dR.equipCooldown)
                                        end
                                    )
                                end
                            end
                        end
                    end
                    if dN["Character"] then
                        for D, fl in ipairs(dN["Character"]:GetChildren()) do
                            if (fl:IsA("Tool") and ig[fl["Name"]] and fl:FindFirstChild("Handle")) then
                                ek(dR.equippedTools, fl)
                            end
                        end
                    end
                end
                local function iq(ir)
                    if dR["toolAddedConn"] then
                        dR["toolAddedConn"]:Disconnect()
                        dR["toolAddedConn"] = nil
                    end
                    if (dR["toolRemovedConn"] or (4048 > 4232)) then
                        dR["toolRemovedConn"]:Disconnect()
                        dR["toolRemovedConn"] = nil
                    end
                    dR["toolAddedConn"] =
                        ir["ChildAdded"]:Connect(
                        function(eQ)
                            if ((eQ:IsA("Tool") and ig[eQ["Name"]] and eQ:FindFirstChild("Handle")) or (1750 >= 3473)) then
                                ek(dR.equippedTools, eQ)
                            end
                        end
                    )
                    dR["toolRemovedConn"] =
                        ir["ChildRemoved"]:Connect(
                        function(eQ)
                            if ((3166 == 3166) and eQ:IsA("Tool")) then
                                for w, fl in ipairs(dR.equippedTools) do
                                    if ((1763 < 3724) and (fl == eQ)) then
                                        ie(dR.equippedTools, w)
                                        break
                                    end
                                end
                            end
                        end
                    )
                end
                f0.hasAllR15Parts = function(self)
                    return ii()
                end
                f0.waitForFullyLoaded = function(self)
                    return ij()
                end
                f0.equipTools = function(self)
                    il()
                end
                f0.setupCharacterTracking = function(self)
                    if dN["Character"] then
                        iq(dN.Character)
                    end
                end
            end
            do
                local function is()
                    if not dR["Enable"] then
                        return
                    end
                    if ((57 <= 2723) and dR["autoBuyModule"] and dR["autoBuyModule"]:isBuyingInProgress()) then
                        return
                    end
                    if (not dN["Character"] or (2070 == 443)) then
                        return
                    end
                    local f7 = dN["Character"]:FindFirstChildOfClass("Humanoid")
                    if (not f7 or (f7["Health"] <= 0)) then
                        return
                    end
                    if (not f0:hasAllR15Parts() or (2705 == 1393)) then
                        return
                    end
                    if not f0:waitForFullyLoaded() then
                        return
                    end
                    local fh = tick()
                    if (((fh - dR["lastReequipTime"]) < dR["equipCooldown"]) or (4601 < 61)) then
                        return
                    end
                    dR["lastReequipTime"] = fh
                    local im = dN["Backpack"]
                    if im then
                        for D, fl in ipairs(im:GetChildren()) do
                            if ((fl:IsA("Tool") and ig[fl["Name"]]) or (1390 >= 4744)) then
                                local io = false
                                for D, ip in ipairs(dR.selectedGuns) do
                                    if (fl["Name"] ~= ip) then
                                    else
                                        io = true
                                        break
                                    end
                                end
                                if (io or (2003 > 3834)) then
                                    pcall(
                                        function()
                                            fl["Parent"] = dN["Character"]
                                        end
                                    )
                                    break
                                end
                            end
                        end
                    end
                end
                local function e1()
                    if (dR["conn"] or (156 > 3913)) then
                        return
                    end
                    fo(
                        function()
                            while dR["Enable"] and not f0:waitForFullyLoaded() do
                                wait(0.1)
                            end
                            if dR["Enable"] then
                                f0:equipTools()
                            end
                        end
                    )
                    f0:setupCharacterTracking()
                    if ((195 == 195) and dR["charAddedConn"]) then
                        dR["charAddedConn"]:Disconnect()
                    end
                    dR["charAddedConn"] =
                        dN["CharacterAdded"]:Connect(
                        function(dS)
                            if ((3105 >= 1796) and dR["Enable"]) then
                                f0:setupCharacterTracking()
                            end
                        end
                    )
                    dR["conn"] =
                        dO:Connect(
                        (
                            newcclosure(
                                function()
                                    is()
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if ((4379 >= 2131) and dR["conn"]) then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    if ((3844 >= 2043) and dR["charAddedConn"]) then
                        dR["charAddedConn"]:Disconnect()
                        dR["charAddedConn"] = nil
                    end
                    if (dR["toolAddedConn"] or (3232 <= 2731)) then
                        dR["toolAddedConn"]:Disconnect()
                        dR["toolAddedConn"] = nil
                    end
                    if ((4905 == 4905) and dR["toolRemovedConn"]) then
                        dR["toolRemovedConn"]:Disconnect()
                        dR["toolRemovedConn"] = nil
                    end
                    for w = #dR["equippedTools"], 1, -1 do
                        dR["equippedTools"][w] = nil
                    end
                end
                f0.startLoop = function(self)
                    e1()
                end
                f0.stopLoop = function(self)
                    e3()
                end
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if (eY or (4136 >= 4411)) then
                    self:startLoop()
                else
                    self:stopLoop()
                end
            end
            f0.setAutoBuyModule = function(self, hb)
                dR["autoBuyModule"] = hb
            end
            f0.setSelectedGuns = function(self, fK)
                dR["selectedGuns"] = fK
            end
            f0.getEquippedTools = function(self)
                return dR["equippedTools"]
            end
            f0.init = function(self)
            end
            return f0
        end
    end,
    Ragebot_Targeting = function()
        return function(dL)
            local f0 = {}
            local ed = dL["targeting"]
            local dR = {
                Enable = false,
                haveTarget = false,
                autoSelectEnable = false,
                autoSelectChecks = nil,
                autoSelectMaxFov = nil,
                autoSelectConn = nil,
                onTargetStateChanged = nil,
                lastAutoSelectCheck = 0
            }
            local function it(d)
                dR["haveTarget"] = d
                if (dR["onTargetStateChanged"] or (2958 == 4017)) then
                    dR.onTargetStateChanged(d)
                end
            end
            local function iu(eC)
                if ((1228 >= 813) and not dR["Enable"]) then
                    return
                end
                if ed["target"] then
                    ed:resetTarget()
                    it(false)
                    return
                end
                local f5 = ed:pickTarget(nil, "Mouse", eC)
                if f5 then
                    it(true)
                else
                    it(false)
                end
            end
            f0.init = function(self)
            end
            f0.setEnable = function(self, eY)
                dR["Enable"] = eY
                if not eY then
                    ed:resetTarget()
                    it(false)
                    if dR["autoSelectConn"] then
                        dR["autoSelectConn"]:Disconnect()
                        dR["autoSelectConn"] = nil
                    end
                elseif ((eY and dR["autoSelectEnable"]) or (3455 > 4050)) then
                    self:setAutoSelect(true, dR.autoSelectChecks, dR.autoSelectMaxFov)
                end
            end
            f0.pickTarget = function(self, eC)
                iu(eC)
            end
            f0.getHaveTarget = function(self)
                return dR["haveTarget"]
            end
            f0.updateTargetState = function(self)
                if (ed["target"] and ed:checkTarget()) then
                    it(true)
                else
                    it(false)
                end
            end
            f0.setAutoSelect = function(self, eY, eC, eF)
                dR["autoSelectEnable"] = eY
                dR["autoSelectChecks"] = eC
                dR["autoSelectMaxFov"] = eF
                if eY then
                    if dR["autoSelectConn"] then
                        dR["autoSelectConn"]:Disconnect()
                        dR["autoSelectConn"] = nil
                    end
                    dR["autoSelectConn"] =
                        dL["heart"]:Connect(
                        (
                            newcclosure(
                                function()
                                    if (not dR["Enable"] or not dR["autoSelectEnable"]) then
                                        return
                                    end
                                    local iv = tick()
                                    if ((243 == 243) and ((iv - dR["lastAutoSelectCheck"]) < 0.05)) then
                                        return
                                    end
                                    dR["lastAutoSelectCheck"] = iv
                                    local eH = ed:pickTarget(dR.autoSelectMaxFov, "Mouse", dR.autoSelectChecks)
                                    local iw = ed["target"]
                                    if ((eH ~= iw) or (271 > 1572)) then
                                        if eH then
                                            it(true)
                                        elseif ((2739 < 3293) and iw) then
                                            ed:resetTarget()
                                            it(false)
                                        end
                                    end
                                end
                            )
                        )
                    )
                elseif dR["autoSelectConn"] then
                    dR["autoSelectConn"]:Disconnect()
                    dR["autoSelectConn"] = nil
                end
            end
            f0.onTargetStateChanged = function(self, ix)
                dR["onTargetStateChanged"] = ix
            end
            return f0
        end
    end,
    Ragebot_TargetingFOV = function()
        return function(dL)
            local iy = {}
            local dN, eg, dP = dL["lp"], dL["userinput"], dL["rnd"]
            local hf = dL["new"]
            local dR = {
                Enable = false,
                size = 100,
                gui = nil,
                outline1 = nil,
                outline2 = nil,
                main = nil,
                gradient = nil,
                updateConn = nil,
                gradientColors = {
                    dL.c3rgb(255, 255, 255),
                    dL.c3rgb(255, 255, 255),
                    dL.c3rgb(255, 255, 255),
                    dL.c3rgb(255, 255, 255)
                }
            }
            local function iz()
                if (not dR["gui"] or not dR["main"]) then
                    return
                end
                local ex = eg:GetMouseLocation()
                local iA = ex["X"] - (dR["size"] / 2)
                local iB = ex["Y"] - (dR["size"] / 2)
                dR["outline1"]["Position"] = UDim2.new(0, iA, 0, iB)
                dR["outline1"]["Size"] = UDim2.new(0, dR.size, 0, dR.size)
                dR["outline2"]["Position"] = UDim2.new(0, iA - 2, 0, iB - 2)
                dR["outline2"]["Size"] = UDim2.new(0, dR["size"] + 4, 0, dR["size"] + 4)
                dR["main"]["Position"] = UDim2.new(0, iA - 1, 0, iB - 1)
                dR["main"]["Size"] = UDim2.new(0, dR["size"] + 2, 0, dR["size"] + 2)
            end
            local function iC()
                if not dR["gui"] then
                    return
                end
                if (dR["gradient"] or (3942 < 1134)) then
                    dR["gradient"]["Color"] =
                        ColorSequence.new(
                        {
                            ColorSequenceKeypoint.new(0, dR["gradientColors"][1]),
                            ColorSequenceKeypoint.new(0.33, dR["gradientColors"][2]),
                            ColorSequenceKeypoint.new(0.66, dR["gradientColors"][3]),
                            ColorSequenceKeypoint.new(1, dR["gradientColors"][4])
                        }
                    )
                end
            end
            iy.create = function(self)
                if dR["gui"] then
                    return
                end
                local iD = dN:WaitForChild("PlayerGui")
                dR["gui"] = hf("ScreenGui")
                dR["gui"]["Name"] = "UnnamedTargetingFOV"
                dR["gui"]["ZIndexBehavior"] = Enum["ZIndexBehavior"]["Sibling"]
                dR["gui"]["ResetOnSpawn"] = false
                dR["gui"]["IgnoreGuiInset"] = true
                dR["gui"]["Parent"] = iD
                dR["outline1"] = hf("Frame")
                dR["outline1"]["Name"] = "Outline1"
                dR["outline1"]["BackgroundTransparency"] = 1
                dR["outline1"]["BorderSizePixel"] = 0
                dR["outline1"]["Size"] = UDim2.new(0, dR.size, 0, dR.size)
                dR["outline1"]["Parent"] = dR["gui"]
                local iE = hf("UICorner")
                iE["CornerRadius"] = UDim.new(2, 8)
                iE["Parent"] = dR["outline1"]
                local iF = hf("UIStroke")
                iF["Color"] = dL.c3rgb(0, 0, 0)
                iF["Thickness"] = 1
                iF["Transparency"] = 0
                iF["Parent"] = dR["outline1"]
                dR["outline2"] = hf("Frame")
                dR["outline2"]["Name"] = "Outline2"
                dR["outline2"]["BackgroundTransparency"] = 1
                dR["outline2"]["BorderSizePixel"] = 0
                dR["outline2"]["Size"] = UDim2.new(0, dR["size"] + 4, 0, dR["size"] + 4)
                dR["outline2"]["Parent"] = dR["gui"]
                local iG = hf("UICorner")
                iG["CornerRadius"] = UDim.new(2, 8)
                iG["Parent"] = dR["outline2"]
                local iH = hf("UIStroke")
                iH["Color"] = dL.c3rgb(0, 0, 0)
                iH["Thickness"] = 1
                iH["Transparency"] = 0
                iH["Parent"] = dR["outline2"]
                dR["main"] = hf("Frame")
                dR["main"]["Name"] = "Main"
                dR["main"]["BackgroundTransparency"] = 1
                dR["main"]["BorderSizePixel"] = 0
                dR["main"]["Size"] = UDim2.new(0, dR["size"] + 2, 0, dR["size"] + 2)
                dR["main"]["Parent"] = dR["gui"]
                local iI = hf("UICorner")
                iI["CornerRadius"] = UDim.new(2, 8)
                iI["Parent"] = dR["main"]
                local iJ = hf("UIStroke")
                iJ["Color"] = dL.c3rgb(255, 255, 255)
                iJ["Thickness"] = 1
                iJ["Transparency"] = 0
                iJ["Parent"] = dR["main"]
                dR["gradient"] = hf("UIGradient")
                dR["gradient"]["Color"] =
                    ColorSequence.new(
                    {
                        ColorSequenceKeypoint.new(0, dR["gradientColors"][1]),
                        ColorSequenceKeypoint.new(0.33, dR["gradientColors"][2]),
                        ColorSequenceKeypoint.new(0.66, dR["gradientColors"][3]),
                        ColorSequenceKeypoint.new(1, dR["gradientColors"][4])
                    }
                )
                dR["gradient"]["Rotation"] = 0
                dR["gradient"]["Parent"] = iJ
                dR["updateConn"] =
                    dP:Connect(
                    (
                        newcclosure(
                            function()
                                if ((dR["Enable"] and dR["gui"] and dR["gui"]["Parent"]) or (2693 == 4973)) then
                                    iz()
                                end
                            end
                        )
                    )
                )
            end
            iy.destroy = function(self)
                if ((2146 == 2146) and dR["updateConn"]) then
                    dR["updateConn"]:Disconnect()
                    dR["updateConn"] = nil
                end
                if dR["gui"] then
                    dR["gui"]:Destroy()
                    dR["gui"] = nil
                    dR["outline1"] = nil
                    dR["outline2"] = nil
                    dR["main"] = nil
                    dR["gradient"] = nil
                end
            end
            iy.setEnable = function(self, eY)
                dR["Enable"] = eY
                if (eY or (2244 == 3224)) then
                    self:create()
                else
                    self:destroy()
                end
            end
            iy.setSize = function(self, iK)
                dR["size"] = iK
                if (dR["Enable"] or (4904 <= 1916)) then
                    iz()
                end
            end
            iy.setGradientColor = function(self, iL, hP)
                if ((iL >= 1) and (iL <= 4)) then
                    dR["gradientColors"][iL] = hP
                    iC()
                end
            end
            iy.init = function(self)
            end
            return iy
        end
    end,
    Ragebot_TargetingVisualise = function()
        return function(dL)
            local hd = {}
            local eh, dP = dL["camera"], dL["rnd"]
            local eg = dL["userinput"]
            local ej, he, hf = dL["v2"], dL["c3rgb"], dL["new"]
            local hg = dL["draw"]
            local ed = dL["targeting"]
            local dN = dL["lp"]
            local dR = {
                Enable = false,
                tracerEnable = false,
                tracerThickness = 1.5,
                highlightEnable = false,
                highlightFillColor = he(255, 255, 255),
                highlightFillTransparency = 0.5,
                highlightOutlineColor = he(0, 0, 0),
                highlightOutlineTransparency = 0,
                viewTargetEnable = false,
                conn = nil,
                highlight = nil,
                currentTarget = nil,
                characterConn = nil
            }
            local hh = {}
            do
                hh["outline"] = hg.new("Line")
                hh["outline"]["Visible"] = false
                hh["outline"]["Color"] = he(0, 0, 0)
                hh["outline"]["Thickness"] = 3
                hh["outline"]["Transparency"] = 1
                hh["main"] = hg.new("Line")
                hh["main"]["Visible"] = false
                hh["main"]["Color"] = he(255, 255, 255)
                hh["main"]["Thickness"] = 1.5
                hh["main"]["Transparency"] = 1
            end
            do
                local function hi()
                    if ((90 <= 1065) and not dR["tracerEnable"]) then
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                        return
                    end
                    local f5 = ed:getTarget()
                    if ((4802 == 4802) and not f5) then
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                        return
                    end
                    local ev = f5:FindFirstChild("HumanoidRootPart")
                    if (not ev or (2280 <= 511)) then
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                        return
                    end
                    local ew, eo = eh:WorldToViewportPoint(ev.Position)
                    if (eo and (ew["Z"] > 0)) then
                        local ex = eg:GetMouseLocation()
                        local iM = ej(ew.X, ew.Y)
                        hh["outline"]["From"] = ex
                        hh["outline"]["To"] = iM
                        hh["outline"]["Visible"] = true
                        hh["main"]["From"] = ex
                        hh["main"]["To"] = iM
                        hh["main"]["Visible"] = true
                    else
                        hh["outline"]["Visible"] = false
                        hh["main"]["Visible"] = false
                    end
                end
                hd["updateTracer"] = hi
            end
            do
                local function iN(f5)
                    if dR["highlight"] then
                        dR["highlight"]:Destroy()
                        dR["highlight"] = nil
                    end
                    if (not f5 or (1676 <= 463)) then
                        return
                    end
                    local iO = hf("Highlight")
                    iO["Name"] = "TargetHighlight"
                    iO["Adornee"] = f5
                    iO["FillColor"] = dR["highlightFillColor"]
                    iO["FillTransparency"] = dR["highlightFillTransparency"]
                    iO["OutlineColor"] = dR["highlightOutlineColor"]
                    iO["OutlineTransparency"] = dR["highlightOutlineTransparency"]
                    iO["DepthMode"] = Enum["HighlightDepthMode"]["AlwaysOnTop"]
                    iO["Parent"] = f5
                    dR["highlight"] = iO
                end
                local function iP()
                    if dR["highlight"] then
                        dR["highlight"]:Destroy()
                        dR["highlight"] = nil
                    end
                    if ((3869 == 3869) and dR["characterConn"]) then
                        dR["characterConn"]:Disconnect()
                        dR["characterConn"] = nil
                    end
                end
                local function iQ(f5)
                    if ((1158 <= 2613) and dR["characterConn"]) then
                        dR["characterConn"]:Disconnect()
                        dR["characterConn"] = nil
                    end
                    local eM = ed:getTargetPlayer()
                    if not eM then
                        return
                    end
                    dR["characterConn"] =
                        eM["CharacterAdded"]:Connect(
                        function(eW)
                            if (not dR["highlightEnable"] or (2364 <= 1999)) then
                                return
                            end
                            local dT = eW:WaitForChild("Humanoid", 5)
                            if (not dT or (4922 < 194)) then
                                return
                            end
                            dR["currentTarget"] = eW
                            iN(eW)
                        end
                    )
                end
                local function iR()
                    if not dR["highlightEnable"] then
                        iP()
                        dR["currentTarget"] = nil
                        return
                    end
                    local f5 = ed:getTarget()
                    if not f5 then
                        iP()
                        dR["currentTarget"] = nil
                        return
                    end
                    if ((dR["currentTarget"] ~= f5) or (2091 < 31)) then
                        dR["currentTarget"] = f5
                        iN(f5)
                        iQ(f5)
                    end
                    if (dR["highlight"] and not dR["highlight"]["Parent"]) then
                        iN(f5)
                    end
                end
                hd["updateHighlight"] = iR
                hd["createHighlight"] = iN
                hd["destroyHighlight"] = iP
            end
            do
                local function iS()
                    if (not dR["viewTargetEnable"] or (2430 >= 4872)) then
                        local f7 = dN["Character"] and dN["Character"]:FindFirstChild("Humanoid")
                        if (f7 and (eh["CameraSubject"] ~= f7)) then
                            eh["CameraSubject"] = f7
                        end
                        return
                    end
                    local f5 = ed:getTarget()
                    if (not f5 or (4770 < 1735)) then
                        local f7 = dN["Character"] and dN["Character"]:FindFirstChild("Humanoid")
                        if f7 then
                            eh["CameraSubject"] = f7
                        end
                        return
                    end
                    local ev = f5:FindFirstChild("HumanoidRootPart")
                    if not ev then
                        local f7 = dN["Character"] and dN["Character"]:FindFirstChild("Humanoid")
                        if f7 then
                            eh["CameraSubject"] = f7
                        end
                        return
                    end
                    if ((eh["CameraSubject"] ~= ev) or (4439 <= 2350)) then
                        eh["CameraSubject"] = ev
                    end
                end
                hd["updateViewTarget"] = iS
            end
            do
                local function e1()
                    if dR["conn"] then
                        return
                    end
                    dR["conn"] =
                        dP:Connect(
                        (
                            newcclosure(
                                function()
                                    if (not dR["Enable"] or (4479 < 4466)) then
                                        return
                                    end
                                    if ((2547 > 1225) and dR["tracerEnable"]) then
                                        hd:updateTracer()
                                    end
                                    if ((4671 > 2674) and dR["highlightEnable"]) then
                                        hd:updateHighlight()
                                    end
                                    if dR["viewTargetEnable"] then
                                        hd:updateViewTarget()
                                    end
                                end
                            )
                        )
                    )
                end
                local function e3()
                    if (dR["conn"] or (3696 < 3327)) then
                        dR["conn"]:Disconnect()
                        dR["conn"] = nil
                    end
                    hh["outline"]["Visible"] = false
                    hh["main"]["Visible"] = false
                    if (dR["highlight"] or (4542 == 2970)) then
                        dR["highlight"]:Destroy()
                        dR["highlight"] = nil
                    end
                    if ((252 <= 1977) and dR["characterConn"]) then
                        dR["characterConn"]:Disconnect()
                        dR["characterConn"] = nil
                    end
                    local f7 = dN["Character"] and dN["Character"]:FindFirstChild("Humanoid")
                    if f7 then
                        eh["CameraSubject"] = f7
                    end
                end
                hd["startLoop"] = e1
                hd["stopLoop"] = e3
            end
            local function hN()
                local hO = dR["tracerEnable"] or dR["highlightEnable"] or dR["viewTargetEnable"]
                if ((hO and not dR["Enable"]) or (1436 == 3775)) then
                    dR["Enable"] = true
                    hd:startLoop()
                elseif (not hO and dR["Enable"]) then
                    dR["Enable"] = false
                    hd:stopLoop()
                end
            end
            hd.setTracerEnable = function(self, eY)
                dR["tracerEnable"] = eY
                if (not eY or (1618 < 930)) then
                    hh["outline"]["Visible"] = false
                    hh["main"]["Visible"] = false
                end
                hN()
            end
            hd.setHighlightEnable = function(self, eY)
                dR["highlightEnable"] = eY
                if ((4723 > 4153) and not eY) then
                    hd:destroyHighlight()
                    dR["currentTarget"] = nil
                end
                hN()
            end
            hd.setOutlineColor = function(self, hP, hQ)
                hh["outline"]["Color"] = hP
                hh["outline"]["Transparency"] = 1 - hQ
            end
            hd.setMainColor = function(self, hP, hQ)
                hh["main"]["Color"] = hP
                hh["main"]["Transparency"] = 1 - hQ
            end
            hd.setThickness = function(self, iT)
                dR["tracerThickness"] = iT
                hh["main"]["Thickness"] = iT
                hh["outline"]["Thickness"] = iT + 1.5
            end
            hd.setHighlightFillColor = function(self, hP, hQ)
                dR["highlightFillColor"] = hP
                dR["highlightFillTransparency"] = hQ
                if dR["highlight"] then
                    dR["highlight"]["FillColor"] = hP
                    dR["highlight"]["FillTransparency"] = hQ
                end
            end
            hd.setHighlightOutlineColor = function(self, hP, hQ)
                dR["highlightOutlineColor"] = hP
                dR["highlightOutlineTransparency"] = hQ
                if dR["highlight"] then
                    dR["highlight"]["OutlineColor"] = hP
                    dR["highlight"]["OutlineTransparency"] = hQ
                end
            end
            hd.setViewTargetEnable = function(self, eY)
                dR["viewTargetEnable"] = eY
                if not eY then
                    local f7 = dN["Character"] and dN["Character"]:FindFirstChild("Humanoid")
                    if f7 then
                        eh["CameraSubject"] = f7
                    end
                end
                hN()
            end
            hd.init = function(self)
            end
            return hd
        end
    end,
    Visuals_Auras = function()
        return function(dL)
            local f0 = {}
            local dN, fo, wait, iU, hf = dL["lp"], dL["spawn"], dL["wait"], dL["c3rgb"], dL["new"]
            local ek, ej = dL["insert"], dL["v2"]
            local dQ, iV, iW, iX, iY = dL["cf"], dL["nr"], dL["ns"], dL["nsk"], dL["cs"]
            local iZ, i_, j0 = false, {}, iU(133, 220, 255)
            local j1, j2 = {}, {}
            local j3 = nil
            local function j4()
                for w = 1, #j1 do
                    if ((j1[w] and j1[w]["Parent"]) or (3654 >= 4654)) then
                        j1[w]:Destroy()
                    end
                end
                j1, j2 = {}, {}
            end
            local function j5()
                for w = 1, #j2 do
                    if ((951 <= 1496) and j2[w] and j2[w]["Parent"]) then
                        j2[w]["Color"] = iY(j0)
                    end
                end
            end
            local function j6(j7)
                local j8 = hf("ParticleEmitter")
                for j9, ja in pairs(j7) do
                    j8[j9] = ja
                end
                return j8
            end
            local function jb()
                local dS = dN["Character"]
                if not dS then
                    return
                end
                local dX = dS:FindFirstChild("Torso") or dS:FindFirstChild("UpperTorso")
                if (not dX or (1736 == 571)) then
                    return
                end
                local jc = hf("Attachment")
                jc["CFrame"] = dQ(-1.012, 0.5, 0.852, 0.966, 0, 0.259, 0, 1, 0, -0.259, 0, 0.966)
                jc["Parent"] = dX
                ek(j1, jc)
                local jd = hf("ParticleEmitter")
                jd["Lifetime"] = iV(1, 1)
                jd["LockedToPart"] = true
                jd["Transparency"] = iW({iX(0, 0.944), iX(0.2, 0), iX(0.8, 0), iX(1, 1)})
                jd["LightEmission"] = 1
                jd["Color"] = iY(j0)
                jd["Speed"] = iV(0.05, 0.05)
                jd["Size"] = iW(2.75, 3.5)
                jd["Rate"] = 4
                jd["Texture"] = "http://www.roblox.com/asset/?id=13267054240"
                jd["EmissionDirection"] = Enum["NormalId"]["Back"]
                jd["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jd["Rotation"] = iV(-15, -15)
                jd["Parent"] = jc
                ek(j2, jd)
                local je = hf("Attachment")
                je["CFrame"] = dQ(1.167, 0.5, 0.852, 0.966, 0, -0.259, 0, 1, 0, 0.259, 0, 0.966)
                je["Parent"] = dX
                ek(j1, je)
                local jf = hf("ParticleEmitter")
                jf["Lifetime"] = iV(1, 1)
                jf["LockedToPart"] = true
                jf["Transparency"] = iW({iX(0, 0.944), iX(0.2, 0), iX(0.8, 0), iX(1, 1)})
                jf["LightEmission"] = 1
                jf["Color"] = iY(j0)
                jf["Speed"] = iV(0.05, 0.05)
                jf["Size"] = iW(2.75, 3.5)
                jf["Rate"] = 4
                jf["Texture"] = "http://www.roblox.com/asset/?id=13267054240"
                jf["EmissionDirection"] = Enum["NormalId"]["Front"]
                jf["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jf["Rotation"] = iV(-15, -15)
                jf["Parent"] = je
                ek(j2, jf)
                local jg = hf("Attachment")
                jg["CFrame"] = dQ(0, 0.3, 0)
                jg["Parent"] = dX
                ek(j1, jg)
                local jh = hf("ParticleEmitter")
                jh["Lifetime"] = iV(2, 2)
                jh["FlipbookLayout"] = Enum["ParticleFlipbookLayout"]["Grid4x4"]
                jh["SpreadAngle"] = ej(180, 180)
                jh["LockedToPart"] = true
                jh["Transparency"] = iW({iX(0, 1), iX(0.5, 0.3), iX(1, 1)})
                jh["LightEmission"] = 1
                jh["Color"] = iY(j0)
                jh["VelocitySpread"] = 180
                jh["Speed"] = iV(0.5, 0.5)
                jh["Brightness"] = 2
                jh["Size"] = iW(3, 4)
                jh["Rate"] = 5
                jh["Texture"] = "rbxassetid://11402221943"
                jh["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                jh["Rotation"] = iV(0, 360)
                jh["Parent"] = jg
                ek(j2, jh)
            end
            local function ji()
                local dS = dN["Character"]
                if (not dS or (896 > 4769)) then
                    return
                end
                local ev = dS:FindFirstChild("HumanoidRootPart")
                if not ev then
                    return
                end
                local jj = hf("Attachment")
                jj["CFrame"] = dQ(0, -2.75, 0)
                jj["Parent"] = ev
                ek(j1, jj)
                local jk = hf("ParticleEmitter")
                jk["Lifetime"] = iV(2, 2)
                jk["SpreadAngle"] = ej(0.001, 0.001)
                jk["LockedToPart"] = true
                jk["Transparency"] = iW(0, 1)
                jk["LightEmission"] = 1
                jk["Color"] = iY(j0)
                jk["VelocitySpread"] = 0.001
                jk["Squash"] = iW(0)
                jk["Speed"] = iV(0.001, 0.001)
                jk["Brightness"] = 2
                jk["Size"] = iW({iX(0, 0), iX(0.3, 1), iX(0.6, 2.5), iX(0.8, 4), iX(1, 6)})
                jk["RotSpeed"] = iV(-600, 600)
                jk["Texture"] = "https://assetgame.roblox.com/asset/?id=12713358087&assetName=crescent"
                jk["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jk["Rotation"] = iV(0, 360)
                jk["Parent"] = jj
                ek(j2, jk)
                local jl = hf("ParticleEmitter")
                jl["Lifetime"] = iV(2, 2)
                jl["SpreadAngle"] = ej(0.001, 0.001)
                jl["LockedToPart"] = true
                jl["Transparency"] = iW({iX(0, 0), iX(0.6, 0.2), iX(1, 1)})
                jl["LightEmission"] = 1
                jl["Color"] = iY(j0)
                jl["VelocitySpread"] = 0.001
                jl["Squash"] = iW(0, 2)
                jl["Speed"] = iV(0.001, 0.001)
                jl["Brightness"] = 2
                jl["Size"] = iW({iX(0, 0), iX(0.3, 1), iX(0.6, 2.5), iX(0.8, 4), iX(1, 6)})
                jl["RotSpeed"] = iV(-30, 30)
                jl["Texture"] = "rbxassetid://7216849325"
                jl["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jl["Rotation"] = iV(0, 360)
                jl["Parent"] = jj
                ek(j2, jl)
                local jm = hf("ParticleEmitter")
                jm["Lifetime"] = iV(2, 2)
                jm["SpreadAngle"] = ej(0.001, 0.001)
                jm["LockedToPart"] = true
                jm["Transparency"] = iW({iX(0, 1), iX(0.2, 0.3), iX(1, 1)})
                jm["LightEmission"] = 1
                jm["Color"] = iY(j0)
                jm["VelocitySpread"] = 0.001
                jm["Squash"] = iW(0)
                jm["Speed"] = iV(0.001, 0.001)
                jm["Brightness"] = 2
                jm["Size"] = iW({iX(0, 0), iX(0.3, 2), iX(0.6, 5), iX(0.8, 8), iX(1, 12)})
                jm["RotSpeed"] = iV(-40, 40)
                jm["Texture"] = "rbxassetid://7216855136"
                jm["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jm["Rotation"] = iV(0, 360)
                jm["Parent"] = jj
                ek(j2, jm)
            end
            local function jn()
                local dS = dN["Character"]
                if not dS then
                    return
                end
                local g8 = dS:FindFirstChild("Head")
                if not g8 then
                    return
                end
                local jj = hf("Attachment")
                jj["CFrame"] = dQ(-0.25, 0.933, 0.259, 0.469, -0.25, -0.847, -0.117, 0.933, -0.34, 0.875, 0.259, 0.408)
                jj["Parent"] = g8
                ek(j1, jj)
                local jo = hf("ParticleEmitter")
                jo["Lifetime"] = iV(1, 1)
                jo["SpreadAngle"] = ej(5, 5)
                jo["LockedToPart"] = true
                jo["Transparency"] = iW({iX(0, 1), iX(0.2, 0), iX(0.8, 0), iX(1, 1)})
                jo["LightEmission"] = 1
                jo["Color"] = iY(j0)
                jo["VelocitySpread"] = 5
                jo["Speed"] = iV(0.001, 0.001)
                jo["Brightness"] = 2
                jo["Size"] = iW(2.5, 3)
                jo["RotSpeed"] = iV(-400, 400)
                jo["Rate"] = 7
                jo["Texture"] = "rbxassetid://8819682608"
                jo["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jo["Rotation"] = iV(0, 360)
                jo["Parent"] = jj
                ek(j2, jo)
                local jp = hf("ParticleEmitter")
                jp["Lifetime"] = iV(1, 1)
                jp["SpreadAngle"] = ej(5, 5)
                jp["LockedToPart"] = true
                jp["Transparency"] = iW({iX(0, 1), iX(0.2, 0), iX(0.8, 0), iX(1, 1)})
                jp["LightEmission"] = 1
                jp["Color"] = iY(j0)
                jp["VelocitySpread"] = 5
                jp["Speed"] = iV(0.001, 0.001)
                jp["Brightness"] = 2
                jp["Size"] = iW(2, 3)
                jp["RotSpeed"] = iV(-400, 400)
                jp["Rate"] = 7
                jp["Texture"] = "rbxassetid://8819682608"
                jp["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                jp["Rotation"] = iV(0, 360)
                jp["Parent"] = jj
                ek(j2, jp)
            end
            local function jq()
                local dS = dN["Character"]
                if (not dS or (1045 <= 1020)) then
                    return
                end
                local ev = dS:FindFirstChild("HumanoidRootPart")
                if (not ev or (1160 <= 328)) then
                    return
                end
                local jj = hf("Attachment")
                jj["CFrame"] = dQ(0, -3, 0)
                jj["Parent"] = ev
                ek(j1, jj)
                local dX = hf("ParticleEmitter")
                dX["LightInfluence"] = 1
                dX["LockedToPart"] = true
                dX["LightEmission"] = 1
                dX["Color"] = iY(j0)
                dX["Speed"] = iV(0.01, 0.01)
                dX["Size"] = iW(6, 10)
                dX["RotSpeed"] = iV(360, 360)
                dX["Rate"] = 1
                dX["Texture"] = "http://www.roblox.com/asset/?id=8553497052"
                dX["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                dX["Parent"] = jj
                ek(j2, dX)
            end
            local function jr()
                if ((3808 > 2924) and not iZ) then
                    j4()
                    return
                end
                j4()
                if ((3891 < 4919) and i_["Angelic"]) then
                    jb()
                end
                if i_["Ambient"] then
                    ji()
                end
                if i_["Nimb"] then
                    jn()
                end
                if (i_["Tornado"] or (2234 <= 1502)) then
                    jq()
                end
            end
            local function js()
                if (iZ or (2512 < 432)) then
                    wait(0.5)
                    jr()
                end
            end
            f0.init = function(self)
                if ((dN["Character"] and iZ) or (1848 == 865)) then
                    fo(
                        function()
                            wait(0.5)
                            jr()
                        end
                    )
                end
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                if jt then
                    if not j3 then
                        j3 = dN["CharacterAdded"]:Connect(js)
                    end
                elseif (j3 or (4682 <= 4541)) then
                    j3:Disconnect()
                    j3 = nil
                end
                jr()
            end
            f0.setAuraTypes = function(self, dX)
                i_ = dX
                jr()
            end
            f0.setAuraColor = function(self, ju)
                j0 = ju
                if (iZ and (#j2 > 0)) then
                    j5()
                end
            end
            return f0
        end
    end,
    Visuals_BulletTracers = function()
        return function(dL)
            local f0 = {}
            local eh, jv = dL["camera"], dL["workspace"]
            local fo, jw = dL["spawn"], dL["delay"]
            local iU, hf, hg, ej, f2 = dL["c3rgb"], dL["new"], dL["draw"], dL["v2"], dL["v3"]
            local dP = dL["rnd"]
            local ek, ie = dL["insert"], dL["remove"]
            local iZ, j0, jx, eG = false, iU(155, 125, 175), 0, "Beam"
            local jy, iK, jz = "rbxassetid://446111271", 1, 3
            local jA, jB = nil, nil
            local jC = {}
            local jD = nil
            local jE = 50
            local function jF(jG, jH)
                local jI = hf("Part")
                jI["Size"], jI["Transparency"], jI["CanCollide"], jI["Anchored"], jI["Massless"] =
                    f2(0, 0, 0),
                    1,
                    false,
                    true,
                    true
                jI["Position"], jI["Parent"] = jG, jA
                local jJ = hf("Part")
                jJ["Size"], jJ["Transparency"], jJ["CanCollide"], jJ["Anchored"], jJ["Massless"] =
                    f2(0, 0, 0),
                    1,
                    false,
                    true,
                    true
                jJ["Position"], jJ["Parent"] = jH, jA
                local jK = hf("Beam")
                jK["Attachment0"], jK["Attachment1"] = hf("Attachment", jI), hf("Attachment", jJ)
                jK["LightEmission"], jK["LightInfluence"] = 6, 1
                jK["Width0"], jK["Width1"] = iK, iK
                jK["Texture"], jK["TextureSpeed"], jK["TextureLength"] = jy, 1, 1
                jK["Transparency"], jK["Color"] = NumberSequence.new(jx), ColorSequence.new(j0)
                jK["Parent"] = jI
                jw(
                    jz,
                    function()
                        if (jI["Parent"] or (3026 >= 4046)) then
                            jI:Destroy()
                        end
                        if jJ["Parent"] then
                            jJ:Destroy()
                        end
                    end
                )
            end
            local function jL()
                for w = #jC, 1, -1 do
                    local jM = jC[w]
                    if ((2008 > 638) and ((tick() - jM["startTime"]) >= jz)) then
                        jM["line"]:Remove()
                        ie(jC, w)
                    else
                        local jN, jO = eh:WorldToViewportPoint(jM.sPos)
                        local jP, jQ = eh:WorldToViewportPoint(jM.ePos)
                        if (jO and jQ) then
                            jM["line"]["Visible"] = true
                            jM["line"]["From"] = ej(jN.X, jN.Y)
                            jM["line"]["To"] = ej(jP.X, jP.Y)
                            jM["line"]["Color"] = j0
                            jM["line"]["Transparency"] = 1 - jx
                        else
                            jM["line"]["Visible"] = false
                        end
                    end
                end
            end
            local function jR(jG, jH)
                if (#jC < jE) then
                else
                    local jS = jC[1]
                    if (jS and jS["line"]) then
                        jS["line"]:Remove()
                    end
                    ie(jC, 1)
                end
                local jT = hg.new("Line")
                jT["Color"] = j0
                jT["Visible"] = false
                jT["Transparency"] = 1 - jx
                jT["Thickness"] = 1.3
                jT["ZIndex"] = 3
                ek(jC, {line = jT, sPos = jG, ePos = jH, startTime = tick()})
                if ((1775 <= 3233) and not jD) then
                    jD =
                        dP:Connect(
                        (
                            newcclosure(
                                function()
                                    jL()
                                end
                            )
                        )
                    )
                end
            end
            f0.init = function(self, e4)
                jA = hf("Folder")
                jA["Name"], jA["Parent"] = "BulletTracers", jv
                e4:register(
                    "BulletTracers",
                    function(ea)
                        if ((ea[1] == "ShootGun") and iZ and ea[3] and ea[4]) then
                            fo(
                                function()
                                    pcall(((eG == "Beam") and jF) or jR, ea[3], ea[4])
                                end
                            )
                        end
                    end
                )
            end
            local function jU()
                if (jB or (4543 == 1997)) then
                    return
                end
                jB =
                    dP:Connect(
                    (
                        newcclosure(
                            function()
                                if not iZ then
                                    return
                                end
                                local jV = jv["Ignored"] and jv["Ignored"]["Siren"] and jv["Ignored"]["Siren"]["Radius"]
                                if (jV or (3102 < 728)) then
                                    for D, eQ in pairs(jV:GetChildren()) do
                                        if ((345 == 345) and (eQ["Name"] == "BULLET_RAYS")) then
                                            eQ:Destroy()
                                        end
                                    end
                                end
                            end
                        )
                    )
                )
            end
            local function jW()
                if jB then
                    jB:Disconnect()
                    jB = nil
                end
                if (jD or (2827 < 378)) then
                    jD:Disconnect()
                    jD = nil
                end
                for w = #jC, 1, -1 do
                    if (jC[w] and jC[w]["line"]) then
                        jC[w]["line"]:Remove()
                    end
                end
                jC = {}
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                if (jt or (3476 < 2597)) then
                    jU()
                else
                    jW()
                end
            end
            f0.setColor = function(self, ju, jj)
                j0, jx = ju, jj or 0
            end
            f0.setMode = function(self, jX)
                eG = jX
            end
            f0.setTexture = function(self, dX)
                jy = dX
            end
            f0.setSize = function(self, jt)
                iK = jt
            end
            f0.setLifetime = function(self, jY)
                jz = jY
            end
            return f0
        end
    end,
    Visuals_Crosshair = function()
        return function(dL)
            local f0 = {}
            local dN, hf, dP, jZ, ej, eh = dL["lp"], dL["new"], dL["rnd"], dL["mouse"], dL["v2"], dL["camera"]
            local iZ, j_, k0, k1 = false, nil, nil, nil
            local k2, k3, k4, k5, x, y, k6, k7
            local k8, k9, ka, kb
            local kc, kd, ke, kf = 2, 5, 10, 1
            local kg, kh, ki = false, false, 1
            local kj = false
            local kk, kl = 0, 1
            local km, kn, iU, ko =
                dL.c3rgb(255, 255, 255),
                dL.c3rgb(255, 255, 255),
                dL.c3rgb(255, 255, 255),
                dL.c3rgb(255, 255, 255)
            local kp, kq = dL.c3rgb(255, 255, 255), dL.c3rgb(255, 255, 255)
            local function kr()
                if j_ then
                    return
                end
                j_ = hf("ScreenGui")
                j_["ResetOnSpawn"], j_["ZIndexBehavior"], j_["DisplayOrder"] =
                    false,
                    Enum["ZIndexBehavior"]["Sibling"],
                    18000000000000000000
                k0 = hf("Frame")
                k0["Parent"], k0["BackgroundTransparency"], k0["BorderSizePixel"] = j_, 1, 0
                k0["AnchorPoint"], k0["Size"], k0["ZIndex"] =
                    ej(0.5, 0.5),
                    UDim2.new(0, 50, 0, 50),
                    18000000000000000000
                k8 = hf("Frame")
                k8["Name"] = "IndicatorHolder"
                k8["Parent"] = j_
                k8["BackgroundTransparency"] = 1
                k8["BorderSizePixel"] = 0
                k8["Size"] = UDim2.new(0, 100, 0, 20)
                k8["AnchorPoint"] = ej(0.5, 0)
                k9 = hf("TextLabel")
                k9["Name"] = "IndicatorLabel"
                k9["Parent"] = k8
                k9["BackgroundTransparency"] = 1
                k9["BorderSizePixel"] = 0
                k9["Size"] = UDim2.new(1, 0, 1, 0)
                k9["Font"] = Enum["Font"]["Code"]
                k9["Text"] = "intellect.club"
                k9["TextColor3"] = dL.c3rgb(255, 255, 255)
                k9["TextSize"] = 13
                k9["TextStrokeTransparency"] = 0.1
                k9["TextXAlignment"] = Enum["TextXAlignment"]["Center"]
                k9["TextYAlignment"] = Enum["TextYAlignment"]["Center"]
                k9["ZIndex"] = 18000000000000000000
                k9["Visible"] = kj
                kb = hf("ImageLabel")
                kb["Name"] = "glow"
                kb["Parent"] = k9
                kb["BackgroundTransparency"] = 1
                kb["BorderSizePixel"] = 0
                kb["AnchorPoint"] = ej(0.5, 0.5)
                kb["Position"] = UDim2.new(0.5, 0, 0.6, 0)
                kb["Size"] = UDim2.new(2, 0, 1.5, 0)
                kb["ZIndex"] = 0
                kb["Image"] = "rbxassetid://113581364214844"
                kb["ImageTransparency"] = 0.82
                kb["Visible"] = true
                ka = hf("UIGradient")
                ka["Parent"] = k9
                ka["Color"] = ColorSequence.new({ColorSequenceKeypoint.new(0, kp), ColorSequenceKeypoint.new(1, kq)})
                k2 = hf("Frame")
                k2["Parent"], k2["BackgroundColor3"], k2["BorderSizePixel"], k2["ZIndex"] =
                    k0,
                    km,
                    0,
                    18000000000000000000
                k2["AnchorPoint"] = ej(0, 0.5)
                x = hf("UIStroke")
                x["Parent"], x["Color"], x["Thickness"], x["LineJoinMode"] =
                    k2,
                    dL.c3rgb(0, 0, 0),
                    kf,
                    Enum["LineJoinMode"]["Miter"]
                k3 = hf("Frame")
                k3["Parent"], k3["BackgroundColor3"], k3["BorderSizePixel"], k3["ZIndex"] =
                    k0,
                    kn,
                    0,
                    18000000000000000000
                k3["AnchorPoint"] = ej(0, 0.5)
                y = hf("UIStroke")
                y["Parent"], y["Color"], y["Thickness"], y["LineJoinMode"] =
                    k3,
                    dL.c3rgb(0, 0, 0),
                    kf,
                    Enum["LineJoinMode"]["Miter"]
                k4 = hf("Frame")
                k4["Parent"], k4["BackgroundColor3"], k4["BorderSizePixel"], k4["ZIndex"] =
                    k0,
                    iU,
                    0,
                    18000000000000000000
                k4["AnchorPoint"] = ej(0.5, 0)
                k6 = hf("UIStroke")
                k6["Parent"], k6["Color"], k6["Thickness"], k6["LineJoinMode"] =
                    k4,
                    dL.c3rgb(0, 0, 0),
                    kf,
                    Enum["LineJoinMode"]["Miter"]
                k5 = hf("Frame")
                k5["Parent"], k5["BackgroundColor3"], k5["BorderSizePixel"], k5["ZIndex"] =
                    k0,
                    ko,
                    0,
                    18000000000000000000
                k5["AnchorPoint"] = ej(0.5, 0)
                k7 = hf("UIStroke")
                k7["Parent"], k7["Color"], k7["Thickness"], k7["LineJoinMode"] =
                    k5,
                    dL.c3rgb(0, 0, 0),
                    kf,
                    Enum["LineJoinMode"]["Miter"]
                f0:updateDim()
            end
            f0.updateDim = function(self)
                if not k2 then
                    return
                end
                k2["Position"], k2["Size"] = UDim2.new(0.5, -kd - ke, 0.5, 0), UDim2.new(0, ke, 0, kc)
                k3["Position"], k3["Size"] = UDim2.new(0.5, kd, 0.5, 0), UDim2.new(0, ke, 0, kc)
                k4["Position"], k4["Size"] = UDim2.new(0.5, 0, 0.5, -kd - ke), UDim2.new(0, kc, 0, ke)
                k5["Position"], k5["Size"] = UDim2.new(0.5, 0, 0.5, kd), UDim2.new(0, kc, 0, ke)
                if x then
                    x["Thickness"] = kf
                end
                if y then
                    y["Thickness"] = kf
                end
                if ((3079 < 4794) and k6) then
                    k6["Thickness"] = kf
                end
                if ((4854 > 4464) and k7) then
                    k7["Thickness"] = kf
                end
            end
            local function ks(gb)
                if (not k0 or not kh) then
                    return
                end
                kk = kk + (ki * 60 * gb * kl)
                if ((kk >= 360) or (4912 == 3758)) then
                    kk, kl = 360, -1
                elseif ((126 <= 3482) and (kk <= 0)) then
                    kk, kl = 0, 1
                end
                k0["Rotation"] = kk
            end
            local function kt()
                if (not k0 or not iZ or not j_) then
                    return
                end
                if (kg or (2374 == 4374)) then
                    local hX, hY = jZ["X"], jZ["Y"]
                    k0["Position"] = UDim2.new(0, hX, 0, hY)
                    if k8 then
                        k8["Position"] = UDim2.new(0, hX, 0, hY + kd + ke + 6)
                    end
                else
                    k0["Position"] = UDim2.new(0.5, 0, 0.5, -28)
                    if ((1575 == 1575) and k8) then
                        k8["Position"] = UDim2.new(0.5, 0, 0.5, -28 + kd + ke + 6)
                    end
                end
            end
            f0.show = function(self)
                if not j_ then
                    kr()
                end
                if j_ then
                    j_["Parent"] = dN:WaitForChild("PlayerGui")
                    iZ = true
                    if not k1 then
                        k1 =
                            dP:Connect(
                            (
                                newcclosure(
                                    function(gb)
                                        ks(gb)
                                        kt()
                                    end
                                )
                            )
                        )
                    end
                end
            end
            f0.hide = function(self)
                if j_ then
                    j_["Parent"] = nil
                    iZ = false
                    if k1 then
                        k1:Disconnect()
                        k1 = nil
                    end
                end
            end
            f0.setEnable = function(self, jt)
                if (jt or (2234 == 1455)) then
                    f0:show()
                else
                    f0:hide()
                end
            end
            f0.setChase = function(self, jt)
                kg = jt
            end
            f0.setThickness = function(self, ja)
                kc = ja
                f0:updateDim()
            end
            f0.setLength = function(self, ja)
                ke = ja
                f0:updateDim()
            end
            f0.setGap = function(self, ja)
                kd = ja
                f0:updateDim()
            end
            f0.setOutline = function(self, ja)
                kf = ja
                f0:updateDim()
            end
            f0.setRotate = function(self, jt)
                kh = jt
                if ((not jt and k0) or (1067 > 1779)) then
                    k0["Rotation"], kk, kl = 0, 0, 1
                end
            end
            f0.setRotateSpeed = function(self, ja)
                ki = ja
            end
            f0.setColor1 = function(self, ju)
                km = ju
                if k2 then
                    k2["BackgroundColor3"] = ju
                end
            end
            f0.setColor2 = function(self, ju)
                kn = ju
                if ((2161 >= 934) and k3) then
                    k3["BackgroundColor3"] = ju
                end
            end
            f0.setColor3 = function(self, ju)
                iU = ju
                if k4 then
                    k4["BackgroundColor3"] = ju
                end
            end
            f0.setColor4 = function(self, ju)
                ko = ju
                if ((1612 == 1612) and k5) then
                    k5["BackgroundColor3"] = ju
                end
            end
            f0.setIndicator = function(self, jt)
                kj = jt
                if k9 then
                    k9["Visible"] = jt
                end
            end
            f0.setIndicatorColor1 = function(self, ju)
                kp = ju
                if ka then
                    ka["Color"] =
                        ColorSequence.new({ColorSequenceKeypoint.new(0, kp), ColorSequenceKeypoint.new(1, kq)})
                end
            end
            f0.setIndicatorColor2 = function(self, ju)
                kq = ju
                if ka then
                    ka["Color"] =
                        ColorSequence.new({ColorSequenceKeypoint.new(0, kp), ColorSequenceKeypoint.new(1, kq)})
                end
            end
            f0.setIndicatorText = function(self, dX)
                if k9 then
                    k9["Text"] = dX
                end
            end
            return f0
        end
    end,
    Visuals_ESP = function()
        return function(dL)
            local ku, kv, eh, dN = dL["players"], dL["runservice"], dL["camera"], dL["lp"]
            local ej, f2, he, hf = dL["v2"], dL["v3"], dL["c3rgb"], dL["new"]
            local ei, hT, kw, el, kx = dL["huge"], dL["min"], dL["max"], dL["floor"], dL["abs"]
            local ek, ie, ky = dL["insert"], dL["remove"], dL["find"]
            local kz, kA = dL["format"], dL["lower"]
            local jv, tick, pairs = dL["workspace"], tick, pairs
            local kB, kC = UDim2["new"], CFrame["new"]
            local kD, kE = ColorSequence["new"], ColorSequenceKeypoint["new"]
            local kF = {}
            do
                local kG = {}
                local j_
                local kH = {}
                local function kI(km, kn, jx)
                    return he(
                        (km["R"] + ((kn["R"] - km["R"]) * jx)) * 255,
                        (km["G"] + ((kn["G"] - km["G"]) * jx)) * 255,
                        (km["B"] + ((kn["B"] - km["B"]) * jx)) * 255
                    )
                end
                local function kJ(kK, kL, kM)
                    if ((4352 >= 2833) and (not kK or (#kK < 4))) then
                        return kD(he(255, 255, 255), he(255, 255, 255))
                    end
                    if (not kL or (3222 < 3073)) then
                        return kD({kE(0, kK[1]), kE(0.33, kK[2]), kE(0.66, kK[3]), kE(1, kK[4])})
                    end
                    local dX = tick() * kM
                    local hF = dX % 4
                    local km, kn, iU, ko = {}, {}, {}, {}
                    for w = 1, 4 do
                        local kN = ((w - 1) - hF) % 4
                        local kO = el(kN) + 1
                        local kP = (kO % 4) + 1
                        local jx = kN - el(kN)
                        local hP = kI(kK[kO], kK[kP], jx)
                        if (w == 1) then
                            km = hP
                        elseif ((744 <= 2942) and (w == 2)) then
                            kn = hP
                        elseif ((w == 3) or (1833 <= 1322)) then
                            iU = hP
                        else
                            ko = hP
                        end
                    end
                    return kD({kE(0, km), kE(0.33, kn), kE(0.66, iU), kE(1, ko)})
                end
                local function kQ()
                    if (not j_ or (3467 <= 1055)) then
                        j_ = hf("ScreenGui")
                        j_["Name"] = "ESP"
                        j_["ResetOnSpawn"] = false
                        j_["IgnoreGuiInset"] = true
                        j_["Parent"] = dN:WaitForChild("PlayerGui")
                    end
                    return j_
                end
                kF.createBox = function(self, eV)
                    local dS = eV["Character"]
                    if not dS then
                        return
                    end
                    local ev = dS:FindFirstChild("HumanoidRootPart")
                    if not ev then
                        return
                    end
                    local aY = kQ()
                    local kR = hf("Frame")
                    kR["Name"] = "Box_" .. eV["Name"]
                    kR["BackgroundTransparency"] = 1
                    kR["Size"] = kB(0, 100, 0, 100)
                    kR["Position"] = kB(0, 0, 0, 0)
                    kR["BorderSizePixel"] = 0
                    kR["Parent"] = aY
                    local kS = hf("UIStroke")
                    kS["Name"] = "Stroke"
                    kS["Thickness"] = 1.1
                    kS["Color"] = he(255, 255, 255)
                    kS["Parent"] = kR
                    local kT = hf("UIGradient")
                    kT["Name"] = "Gradient"
                    kT["Rotation"] = 90
                    kT["Color"] =
                        kD(
                        {
                            kE(0, he(255, 255, 255)),
                            kE(0.33, he(255, 255, 255)),
                            kE(0.66, he(255, 255, 255)),
                            kE(1, he(255, 255, 255))
                        }
                    )
                    kT["Parent"] = kS
                    local kU = hf("Frame")
                    kU["Name"] = "OutlineFrame"
                    kU["BackgroundTransparency"] = 1
                    kU["Size"] = kB(1, 2, 1, 2)
                    kU["Position"] = kB(0, -1, 0, -1)
                    kU["BorderSizePixel"] = 0
                    kU["Parent"] = kR
                    local kV = hf("UIStroke")
                    kV["Name"] = "OutlineStroke"
                    kV["Thickness"] = 0.9
                    kV["Color"] = he(0, 0, 0)
                    kV["Parent"] = kU
                    local kW = hf("Frame")
                    kW["Name"] = "InlineFrame"
                    kW["BackgroundTransparency"] = 1
                    kW["Size"] = kB(1, -2, 1, -2)
                    kW["Position"] = kB(0, 1, 0, 1)
                    kW["BorderSizePixel"] = 0
                    kW["Parent"] = kR
                    local kX = hf("UIStroke")
                    kX["Name"] = "InlineStroke"
                    kX["Thickness"] = 0.9
                    kX["Color"] = he(0, 0, 0)
                    kX["Parent"] = kW
                    local kY = hf("Frame")
                    kY["Name"] = "HealthBarOutline_" .. eV["Name"]
                    kY["BackgroundColor3"] = he(0, 0, 0)
                    kY["BorderSizePixel"] = 0
                    kY["Visible"] = false
                    kY["Parent"] = aY
                    local kZ = hf("UIStroke")
                    kZ["Name"] = "OutlineStroke"
                    kZ["Thickness"] = 0.9
                    kZ["Color"] = he(0, 0, 0)
                    kZ["Parent"] = kY
                    local k_ = hf("Frame")
                    k_["Name"] = "HealthBarFill"
                    k_["BackgroundTransparency"] = 0
                    k_["BorderSizePixel"] = 0
                    k_["AnchorPoint"] = ej(0, 1)
                    k_["Position"] = kB(0, 0, 1, 0)
                    k_["Size"] = kB(1, 0, 1, 0)
                    k_["Parent"] = kY
                    local l0 = hf("UIGradient")
                    l0["Name"] = "HealthBarGradient"
                    l0["Rotation"] = 90
                    l0["Color"] =
                        kD(
                        {kE(0, he(0, 255, 0)), kE(0.33, he(0, 255, 0)), kE(0.66, he(0, 255, 0)), kE(1, he(0, 255, 0))}
                    )
                    l0["Parent"] = k_
                    local l1 = hf("Frame")
                    l1["Name"] = "ArmorBarOutline_" .. eV["Name"]
                    l1["BackgroundColor3"] = he(0, 0, 0)
                    l1["BorderSizePixel"] = 0
                    l1["Visible"] = false
                    l1["Parent"] = aY
                    local l2 = hf("UIStroke")
                    l2["Name"] = "OutlineStroke"
                    l2["Thickness"] = 0.9
                    l2["Color"] = he(0, 0, 0)
                    l2["Parent"] = l1
                    local l3 = hf("Frame")
                    l3["Name"] = "ArmorBarFill"
                    l3["BackgroundTransparency"] = 0
                    l3["BorderSizePixel"] = 0
                    l3["AnchorPoint"] = ej(0, 1)
                    l3["Position"] = kB(0, 0, 1, 0)
                    l3["Size"] = kB(1, 0, 1, 0)
                    l3["Parent"] = l1
                    local l4 = hf("UIGradient")
                    l4["Name"] = "ArmorBarGradient"
                    l4["Rotation"] = 90
                    l4["Color"] =
                        kD(
                        {
                            kE(0, he(0, 150, 255)),
                            kE(0.33, he(0, 150, 255)),
                            kE(0.66, he(0, 150, 255)),
                            kE(1, he(0, 150, 255))
                        }
                    )
                    l4["Parent"] = l3
                    local l5 = hf("ScreenGui")
                    l5["Name"] = "TextContainer_" .. eV["Name"]
                    l5["ResetOnSpawn"] = false
                    l5["IgnoreGuiInset"] = true
                    l5["Parent"] = dN:WaitForChild("PlayerGui")
                    local l6 = hf("TextLabel")
                    l6["Name"] = "NameText"
                    l6["BackgroundTransparency"] = 1
                    l6["BorderSizePixel"] = 0
                    l6["TextColor3"] = he(255, 255, 255)
                    l6["TextStrokeTransparency"] = 0
                    l6["TextStrokeColor3"] = he(0, 0, 0)
                    l6["TextSize"] = 12
                    l6["TextScaled"] = false
                    l6["Text"] = ""
                    l6["TextXAlignment"] = Enum["TextXAlignment"]["Center"]
                    l6["TextYAlignment"] = Enum["TextYAlignment"]["Center"]
                    l6["Visible"] = false
                    l6["Size"] = kB(0, 200, 0, 14)
                    if ((3541 == 3541) and kF["libraryFont"]) then
                        l6["FontFace"] = kF["libraryFont"]
                    end
                    l6["Parent"] = l5
                    local l7 = hf("TextLabel")
                    l7["Name"] = "DistanceText"
                    l7["BackgroundTransparency"] = 1
                    l7["BorderSizePixel"] = 0
                    l7["TextColor3"] = he(255, 255, 255)
                    l7["TextStrokeTransparency"] = 0
                    l7["TextStrokeColor3"] = he(0, 0, 0)
                    l7["TextSize"] = 12
                    l7["TextScaled"] = false
                    l7["Text"] = ""
                    l7["TextXAlignment"] = Enum["TextXAlignment"]["Center"]
                    l7["TextYAlignment"] = Enum["TextYAlignment"]["Center"]
                    l7["Visible"] = false
                    l7["Size"] = kB(0, 200, 0, 14)
                    if (kF["libraryFont"] or (3557 >= 4003)) then
                        l7["FontFace"] = kF["libraryFont"]
                    end
                    l7["Parent"] = l5
                    local l8 = hf("TextLabel")
                    l8["Name"] = "ToolText"
                    l8["BackgroundTransparency"] = 1
                    l8["BorderSizePixel"] = 0
                    l8["TextColor3"] = he(255, 255, 255)
                    l8["TextStrokeTransparency"] = 0
                    l8["TextStrokeColor3"] = he(0, 0, 0)
                    l8["TextSize"] = 12
                    l8["TextScaled"] = false
                    l8["Text"] = ""
                    l8["TextXAlignment"] = Enum["TextXAlignment"]["Center"]
                    l8["TextYAlignment"] = Enum["TextYAlignment"]["Center"]
                    l8["Visible"] = false
                    l8["Size"] = kB(0, 200, 0, 14)
                    if kF["libraryFont"] then
                        l8["FontFace"] = kF["libraryFont"]
                    end
                    l8["Parent"] = l5
                    return {
                        player = eV,
                        box = kR,
                        stroke = kS,
                        gradient = kT,
                        outlineFrame = kU,
                        outlineStroke = kV,
                        inlineFrame = kW,
                        inlineStroke = kX,
                        char = dS,
                        healthBarOutline = kY,
                        healthBarOutlineStroke = kZ,
                        healthBarFill = k_,
                        healthBarGradient = l0,
                        armorBarOutline = l1,
                        armorBarOutlineStroke = l2,
                        armorBarFill = l3,
                        armorBarGradient = l4,
                        textContainer = l5,
                        nameText = l6,
                        distanceText = l7,
                        toolText = l8,
                        lastHealth = 1,
                        lastArmor = 1
                    }
                end
                kF.removeBox = function(self, eV)
                    local l9 = kG[eV]
                    if l9 then
                        if l9["box"] then
                            l9["box"]:Destroy()
                        end
                        if l9["healthBarOutline"] then
                            l9["healthBarOutline"]:Destroy()
                        end
                        if l9["armorBarOutline"] then
                            l9["armorBarOutline"]:Destroy()
                        end
                        if (l9["textContainer"] or (657 >= 1668)) then
                            l9["textContainer"]:Destroy()
                        end
                    end
                    kG[eV] = nil
                end
                local function la(l9)
                    l9["box"]["Visible"] = false
                    if (l9["healthBarOutline"] or (1027 > 3858)) then
                        l9["healthBarOutline"]["Visible"] = false
                    end
                    if l9["armorBarOutline"] then
                        l9["armorBarOutline"]["Visible"] = false
                    end
                    if l9["nameText"] then
                        l9["nameText"]["Visible"] = false
                    end
                    if (l9["distanceText"] or (3654 < 450)) then
                        l9["distanceText"]["Visible"] = false
                    end
                    if l9["toolText"] then
                        l9["toolText"]["Visible"] = false
                    end
                    l9["lastBoxX"] = nil
                    l9["lastBoxY"] = nil
                    l9["lastBoxWidth"] = nil
                    l9["lastBoxHeight"] = nil
                end
                kF.updateBox = function(self, l9, lb)
                    if ((1891 < 4453) and (not l9 or not l9["char"] or not l9["box"])) then
                        return
                    end
                    local dS = l9["char"]
                    if not dS["Parent"] then
                        la(l9)
                        return
                    end
                    local ev = dS:FindFirstChild("HumanoidRootPart")
                    local dT = dS:FindFirstChildOfClass("Humanoid")
                    if (not ev or (3140 < 2129)) then
                        la(l9)
                        return
                    end
                    local lc, eo = eh:WorldToViewportPoint(ev.Position)
                    if (not eo or (2555 < 1240)) then
                        la(l9)
                        return
                    end
                    local ld, le, lf = 2.5, 6, 1.5
                    local lg, lh, li = ld / 2, le / 2, lf / 2
                    local dQ = ev["CFrame"]
                    local lj = {
                        eh:WorldToViewportPoint((dQ * kC(-lg, -lh, -li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(lg, -lh, -li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(-lg, lh, -li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(lg, lh, -li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(-lg, -lh, li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(lg, -lh, li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(-lg, lh, li)).Position),
                        eh:WorldToViewportPoint((dQ * kC(lg, lh, li)).Position)
                    }
                    local lk, ll = ei, ei
                    local lm, ln = -ei, -ei
                    for w = 1, 8 do
                        local lo = lj[w]
                        lk = hT(lk, lo.X)
                        ll = hT(ll, lo.Y)
                        lm = kw(lm, lo.X)
                        ln = kw(ln, lo.Y)
                    end
                    local lp = lm - lk
                    local lq = ln - ll
                    local lr, ls = lk, ll
                    l9["lastBoxX"] = lr
                    l9["lastBoxY"] = ls
                    l9["lastBoxWidth"] = lp
                    l9["lastBoxHeight"] = lq
                    l9["box"]["Visible"] = lb["boxEnable"]
                    if (lb["boxEnable"] or (4727 <= 4722)) then
                        l9["box"]["Position"] = kB(0, lr, 0, ls)
                        l9["box"]["Size"] = kB(0, lp, 0, lq)
                        if (lb["boxColors"] and l9["gradient"]) then
                            l9["gradient"]["Color"] = kJ(lb.boxColors, lb.boxLerp, lb.boxLerpSpeed)
                        end
                    end
                    local fn = (ev["Position"] - eh["CFrame"]["Position"])["Magnitude"]
                    local lt = 4.1 * hT(kw(1 + ((fn / 100) * 0.2), 1), 1.2)
                    local lu = 0.6
                    if
                        ((740 < 4937) and lb["healthEnable"] and dT and l9["healthBarFill"] and l9["healthBarOutline"] and
                            l9["lastBoxX"] and
                            l9["lastBoxY"] and
                            l9["lastBoxWidth"] and
                            l9["lastBoxHeight"])
                     then
                        local lv = hT(dT["Health"] / dT["MaxHealth"], 1)
                        local lw = l9["lastHealth"]
                        if ((3658 >= 280) and not lw) then
                            lw = lv
                        end
                        local lx = lw + ((lv - lw) * 0.05)
                        l9["lastHealth"] = lx
                        local ly = ((l9["lastBoxX"] - lt) - lu) - 1
                        local lz = l9["lastBoxY"] - 1
                        local lA = l9["lastBoxHeight"] + 2
                        l9["healthBarOutline"]["Position"] = kB(0, ly, 0, lz)
                        l9["healthBarOutline"]["Size"] = kB(0, lu + 2, 0, lA)
                        l9["healthBarOutline"]["Visible"] = true
                        l9["healthBarFill"]["Size"] = kB(1, 0, lx, 0)
                        if (lb["healthColors"] and l9["healthBarGradient"]) then
                            l9["healthBarGradient"]["Color"] = kJ(lb.healthColors, lb.healthLerp, lb.healthLerpSpeed)
                        end
                    elseif (l9["healthBarOutline"] or (885 >= 1031)) then
                        l9["healthBarOutline"]["Visible"] = false
                    end
                    if
                        ((3554 >= 525) and lb["armorEnable"] and l9["armorBarFill"] and l9["armorBarOutline"] and
                            l9["lastBoxX"] and
                            l9["lastBoxY"] and
                            l9["lastBoxWidth"] and
                            l9["lastBoxHeight"])
                     then
                        local fw = 0
                        local fu = jv:FindFirstChild("Players")
                        if fu then
                            local fv = fu:FindFirstChild(l9["player"].Name)
                            if fv then
                                local eD = fv:FindFirstChild("BodyEffects")
                                if ((2414 <= 2972) and eD) then
                                    local lB = eD:FindFirstChild("Armor")
                                    if ((3529 <= 3538) and lB and lB:IsA("IntValue")) then
                                        fw = lB["Value"]
                                    end
                                end
                            end
                        end
                        local fz = hT(fw / 130, 1)
                        local lC = l9["lastArmor"]
                        if (not lC or (2861 < 458)) then
                            lC = fz
                        end
                        local lD = lC + ((fz - lC) * 0.05)
                        l9["lastArmor"] = lD
                        local ly = l9["lastBoxX"] + l9["lastBoxWidth"] + lt
                        local lz = l9["lastBoxY"] - 1
                        local lA = l9["lastBoxHeight"] + 2
                        l9["armorBarOutline"]["Position"] = kB(0, ly, 0, lz)
                        l9["armorBarOutline"]["Size"] = kB(0, lu + 2, 0, lA)
                        l9["armorBarOutline"]["Visible"] = true
                        l9["armorBarFill"]["Size"] = kB(1, 0, lD, 0)
                        if (lb["armorColors"] and l9["armorBarGradient"]) then
                            l9["armorBarGradient"]["Color"] = kJ(lb.armorColors, lb.armorLerp, lb.armorLerpSpeed)
                        end
                    elseif ((1717 <= 4525) and l9["armorBarOutline"]) then
                        l9["armorBarOutline"]["Visible"] = false
                    end
                    if
                        ((l9["nameText"] and l9["distanceText"] and l9["toolText"] and l9["lastBoxX"] and l9["lastBoxY"] and
                            l9["lastBoxWidth"] and
                            l9["lastBoxHeight"]) or
                            (3178 <= 1524))
                     then
                        local lE = l9["lastBoxX"] + (l9["lastBoxWidth"] / 2)
                        local lF = l9["lastBoxY"] - 18
                        local lG = l9["lastBoxY"] + l9["lastBoxHeight"] + 4
                        if ((4254 > 370) and lb["nameEnable"]) then
                            l9["nameText"]["Text"] = l9["player"]["Name"]
                            l9["nameText"]["Position"] = kB(0, lE - (l9["nameText"]["AbsoluteSize"]["X"] / 2), 0, lF)
                            l9["nameText"]["TextColor3"] = lb["nameColor"]
                            l9["nameText"]["TextSize"] = lb["nameSize"]
                            if lb["nameFont"] then
                                l9["nameText"]["Font"] = Enum["Font"][lb["nameFont"]]
                            end
                            l9["nameText"]["Visible"] = true
                        else
                            l9["nameText"]["Visible"] = false
                        end
                        if (lb["distanceEnable"] and ev) then
                            local fn = (ev["Position"] - eh["CFrame"]["Position"])["Magnitude"]
                            local lH = el(fn * 0.28)
                            l9["distanceText"]["Text"] = "[" .. lH .. "m]"
                            l9["distanceText"]["Position"] =
                                kB(0, lE - (l9["distanceText"]["AbsoluteSize"]["X"] / 2), 0, lG)
                            l9["distanceText"]["TextColor3"] = lb["distanceColor"]
                            l9["distanceText"]["TextSize"] = lb["distanceSize"]
                            if lb["distanceFont"] then
                                l9["distanceText"]["Font"] = Enum["Font"][lb["distanceFont"]]
                            end
                            l9["distanceText"]["Visible"] = true
                        else
                            l9["distanceText"]["Visible"] = false
                        end
                        if lb["toolEnable"] then
                            local fl = dS:FindFirstChildOfClass("Tool")
                            l9["toolText"]["Text"] = (fl and fl["Name"]) or "None"
                            local lI = (lb["distanceEnable"] and (lG + 14.5)) or lG
                            l9["toolText"]["Position"] = kB(0, lE - (l9["toolText"]["AbsoluteSize"]["X"] / 2), 0, lI)
                            l9["toolText"]["TextColor3"] = lb["toolColor"]
                            l9["toolText"]["TextSize"] = lb["toolSize"]
                            if (lb["toolFont"] or (1635 == 1777)) then
                                l9["toolText"]["Font"] = Enum["Font"][lb["toolFont"]]
                            end
                            l9["toolText"]["Visible"] = true
                        else
                            l9["toolText"]["Visible"] = false
                        end
                    end
                end
                kF.getESP = function(self, eV)
                    return kG[eV]
                end
                kF.setESP = function(self, eV, l9)
                    kG[eV] = l9
                end
                kF.clearAll = function(self)
                    for D, k1 in pairs(kH) do
                        if ((k1 and k1["Disconnect"]) or (3338 >= 3993)) then
                            k1:Disconnect()
                        end
                    end
                    kH = {}
                    for eV, l9 in pairs(kG) do
                        if ((1154 <= 1475) and l9["box"]) then
                            l9["box"]:Destroy()
                        end
                        if l9["healthBarOutline"] then
                            l9["healthBarOutline"]:Destroy()
                        end
                        if (l9["armorBarOutline"] or (2610 < 1230)) then
                            l9["armorBarOutline"]:Destroy()
                        end
                        if (l9["textContainer"] or (1448 == 3083)) then
                            l9["textContainer"]:Destroy()
                        end
                    end
                    kG = {}
                end
                kF.updateAllBoxes = function(self, lb)
                    for eV, l9 in pairs(kG) do
                        kF:updateBox(l9, lb)
                    end
                end
                kF.initAllPlayers = function(self)
                    for D, eV in pairs(ku:GetPlayers()) do
                        if ((3139 > 916) and (eV ~= dN)) then
                            local dS = eV["Character"]
                            if dS then
                                local l9 = kF:createBox(eV)
                                if l9 then
                                    kG[eV] = l9
                                end
                            end
                        end
                    end
                end
                kF.setupPlayerTracking = function(self)
                    kH["playerAdded"] =
                        ku["PlayerAdded"]:Connect(
                        function(eV)
                            if ((2954 == 2954) and (eV == dN)) then
                                return
                            end
                            local function iq(dS)
                                local l9 = kF:createBox(eV)
                                if ((117 <= 2892) and l9) then
                                    kG[eV] = l9
                                end
                            end
                            if (eV["Character"] or (453 > 4662)) then
                                iq(eV.Character)
                            end
                            kH["char_" .. eV["UserId"]] = eV["CharacterAdded"]:Connect(iq)
                        end
                    )
                    kH["playerRemoving"] =
                        ku["PlayerRemoving"]:Connect(
                        function(eV)
                            kF:removeBox(eV)
                            local lJ = "char_" .. eV["UserId"]
                            if kH[lJ] then
                                kH[lJ]:Disconnect()
                                kH[lJ] = nil
                            end
                        end
                    )
                    for D, eV in pairs(ku:GetPlayers()) do
                        if (eV ~= dN) then
                            kH["char_" .. eV["UserId"]] =
                                eV["CharacterAdded"]:Connect(
                                function(dS)
                                    local l9 = kF:createBox(eV)
                                    if ((1320 > 595) and l9) then
                                        kG[eV] = l9
                                    end
                                end
                            )
                        end
                    end
                end
            end
            return kF
        end
    end,
    Visuals_GunChams = function()
        return function(dL)
            local f0 = {}
            local dN, hf, iU = dL["lp"], dL["new"], dL["c3rgb"]
            local hT, kw = dL["min"], dL["max"]
            local wait = dL["wait"]
            local iZ, j0, jx, lK = false, iU(155, 125, 175), 0, "ForceField"
            local lL, lM, lN = "None", iU(255, 255, 255), 0
            local lO = {}
            local j3, lP, lQ = nil, nil, nil
            local function lR(fl)
                if not fl then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if (eJ:IsA("BasePart") or eJ:IsA("MeshPart")) then
                        local jt = eJ:FindFirstChild("stars")
                        if (jt or (3199 < 590)) then
                            jt:Destroy()
                        end
                        local lS = eJ:FindFirstChild("Specks")
                        if (lS or (4793 < 30)) then
                            lS:Destroy()
                        end
                        local lT = eJ:FindFirstChild("Smoke1")
                        if (lT or (1696 <= 1059)) then
                            lT:Destroy()
                        end
                        local lU = eJ:FindFirstChild("Lighting")
                        if lU then
                            lU:Destroy()
                        end
                    end
                end
            end
            local function lV(fl)
                if ((2343 == 2343) and not fl) then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if ((eJ:IsA("BasePart") or eJ:IsA("MeshPart")) and (eJ["Name"] ~= "Handle")) then
                        local j8 = eJ:FindFirstChild("stars")
                        if (j8 or (1043 > 3591)) then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local jt = hf("ParticleEmitter")
                                jt["Name"] = "stars"
                                jt["FlipbookFramerate"] = NumberRange.new(16, 16)
                                jt["Lifetime"] = NumberRange.new(0.45, 0.9)
                                jt["LockedToPart"] = true
                                jt["LightEmission"] = 1
                                jt["Drag"] = 5
                                jt["Squash"] = NumberSequence.new(-0.1)
                                jt["Speed"] = NumberRange.new(0.001, 0.001)
                                jt["Brightness"] = 3
                                jt["ZOffset"] = 1
                                jt["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 0),
                                        NumberSequenceKeypoint.new(0.508, 0.05, 0.05),
                                        NumberSequenceKeypoint.new(1, 0)
                                    }
                                )
                                jt["Rate"] = 150
                                jt["Texture"] = "rbxassetid://1084996976"
                                jt["EmissionDirection"] = Enum["NormalId"]["Bottom"]
                                jt["Color"] = ColorSequence.new(lM)
                                jt["Transparency"] = NumberSequence.new(lN)
                                jt["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lW(fl)
                if (not fl or (2890 >= 4079)) then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if ((4474 <= 4770) and (eJ:IsA("BasePart") or eJ:IsA("MeshPart")) and (eJ["Name"] ~= "Handle")) then
                        local j8 = eJ:FindFirstChild("Specks")
                        if (j8 or (4942 == 3903)) then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lS = hf("ParticleEmitter")
                                lS["Name"] = "Specks"
                                lS["Lifetime"] = NumberRange.new(0.22, 0.22)
                                lS["SpreadAngle"] = Vector2.new(90, 90)
                                lS["Transparency"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, hT(1, lN + 0.8)),
                                        NumberSequenceKeypoint.new(0.25, kw(0, lN - 0.1)),
                                        NumberSequenceKeypoint.new(1, hT(1, lN + 0.8))
                                    }
                                )
                                lS["LightEmission"] = 1
                                lS["Color"] = ColorSequence.new(lM)
                                lS["Drag"] = 5
                                lS["VelocitySpread"] = 90
                                lS["Squash"] = NumberSequence.new(0)
                                lS["Speed"] = NumberRange.new(1, 1)
                                lS["Brightness"] = 4.2
                                lS["Size"] = NumberSequence.new(0.15)
                                lS["Acceleration"] = Vector3.new(0, -15, 0)
                                lS["RotSpeed"] = NumberRange.new(-45, 45)
                                lS["ShapeInOut"] = Enum["ParticleEmitterShapeInOut"]["InAndOut"]
                                lS["Rate"] = 100
                                lS["Texture"] = "rbxassetid://7216849703"
                                lS["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lX(fl)
                if not fl then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if (((eJ:IsA("BasePart") or eJ:IsA("MeshPart")) and (eJ["Name"] ~= "Handle")) or (248 > 4845)) then
                        local j8 = eJ:FindFirstChild("Smoke1")
                        if j8 then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lT = hf("ParticleEmitter")
                                lT["Name"] = "Smoke1"
                                lT["Lifetime"] = NumberRange.new(0.8, 0.8)
                                lT["FlipbookLayout"] = Enum["ParticleFlipbookLayout"]["Grid4x4"]
                                lT["SpreadAngle"] = Vector2.new(0, 360)
                                lT["LockedToPart"] = true
                                lT["Transparency"] = NumberSequence.new(lN)
                                lT["LightEmission"] = 0.5
                                lT["Color"] = ColorSequence.new(lM)
                                lT["Speed"] = NumberRange.new(0, 0)
                                lT["ZOffset"] = 2
                                lT["RotSpeed"] = NumberRange.new(-50, 50)
                                lT["Rate"] = 5
                                lT["Texture"] = "rbxassetid://14006773822"
                                lT["EmissionDirection"] = Enum["NormalId"]["Front"]
                                lT["Orientation"] = Enum["ParticleOrientation"]["FacingCameraWorldUp"]
                                lT["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                                lT["Rotation"] = NumberRange.new(-360, 360)
                                lT["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lY(fl)
                if ((1569 == 1569) and not fl) then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if ((eJ:IsA("BasePart") or eJ:IsA("MeshPart")) and (eJ["Name"] ~= "Handle")) then
                        local j8 = eJ:FindFirstChild("Lighting")
                        if j8 then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lU = hf("ParticleEmitter")
                                lU["Name"] = "Lighting"
                                lU["FlipbookFramerate"] = NumberRange.new(40, 70)
                                lU["Lifetime"] = NumberRange.new(0.5, 1)
                                lU["FlipbookLayout"] = Enum["ParticleFlipbookLayout"]["Grid4x4"]
                                lU["SpreadAngle"] = Vector2.new(360, 360)
                                lU["LockedToPart"] = true
                                lU["Transparency"] = NumberSequence.new(lN)
                                lU["LightEmission"] = -1
                                lU["Color"] = ColorSequence.new(lM)
                                lU["Drag"] = 8
                                lU["VelocitySpread"] = 360
                                lU["Speed"] = NumberRange.new(0.0006561, 0.0006561)
                                lU["Brightness"] = 20
                                lU["ZOffset"] = 1
                                lU["Size"] = NumberSequence.new(0.852325)
                                lU["Rate"] = 5
                                lU["Texture"] = "rbxassetid://17005524119"
                                lU["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                                lU["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                                lU["Rotation"] = NumberRange.new(-360, 360)
                                lU["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lZ(fl)
                if (not iZ or not fl or (4927 <= 3221)) then
                    return
                end
                for D, eJ in pairs(fl:GetChildren()) do
                    if ((eJ["Name"] ~= "Handle") and (eJ:IsA("BasePart") or eJ:IsA("MeshPart"))) then
                        eJ["Material"], eJ["Color"], eJ["Transparency"] = Enum["Material"][lK], j0, jx
                        if eJ:IsA("MeshPart") then
                            eJ["TextureID"] = ""
                        end
                    end
                end
                if ((lL == "Stars") or (1780 > 2787)) then
                    lV(fl)
                elseif (lL == "Particles") then
                    lW(fl)
                elseif ((lL == "Smoke") or (3937 <= 1230)) then
                    lX(fl)
                elseif (lL == "Lighting") then
                    lY(fl)
                else
                    lR(fl)
                end
            end
            local function l_(fl)
                if not fl then
                    return
                end
                lR(fl)
                for D, eJ in pairs(fl:GetChildren()) do
                    if (((eJ["Name"] ~= "Handle") and (eJ:IsA("BasePart") or eJ:IsA("MeshPart"))) or (2637 < 1706)) then
                        eJ["Material"] = Enum["Material"]["Plastic"]
                        eJ["Transparency"] = 0
                    end
                end
            end
            local function m0()
                if not dN["Character"] then
                    return
                end
                for D, ju in pairs(dN["Character"]:GetChildren()) do
                    if ((ju:IsA("Tool") and iZ) or (2669 <= 2409)) then
                        if not lO[ju] then
                            lO[ju] = true
                        end
                        lZ(ju)
                    end
                end
            end
            local function m1(dS)
                if lP then
                    lP:Disconnect()
                end
                if (lQ or (1401 > 4696)) then
                    lQ:Disconnect()
                end
                lP =
                    dS["ChildAdded"]:Connect(
                    function(ju)
                        if ((ju:IsA("Tool") and iZ) or (3280 < 1321)) then
                            lO[ju] = true
                            wait(0.1)
                            lZ(ju)
                        end
                    end
                )
                lQ =
                    dS["ChildRemoved"]:Connect(
                    function(ju)
                        if (ju:IsA("Tool") and lO[ju]) then
                            lO[ju] = nil
                        end
                    end
                )
            end
            f0.init = function(self)
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                if jt then
                    lO = {}
                    if ((4927 >= 2303) and not j3) then
                        j3 =
                            dN["CharacterAdded"]:Connect(
                            function(dS)
                                lO = {}
                                wait(0.5)
                                if iZ then
                                    m0()
                                    m1(dS)
                                end
                            end
                        )
                    end
                    if ((3462 >= 1032) and dN["Character"]) then
                        m0()
                        m1(dN.Character)
                    end
                else
                    if j3 then
                        j3:Disconnect()
                        j3 = nil
                    end
                    if (lP or (1077 >= 2011)) then
                        lP:Disconnect()
                        lP = nil
                    end
                    if lQ then
                        lQ:Disconnect()
                        lQ = nil
                    end
                    for dX, D in pairs(lO) do
                        if (dX and dX["Parent"]) then
                            l_(dX)
                        end
                    end
                    lO = {}
                end
            end
            f0.setColor = function(self, ju, jj)
                j0, jx = ju, jj
                if iZ then
                    m0()
                end
            end
            f0.setParticleColor = function(self, ju, jj)
                lM, lN = ju, jj
                if iZ then
                    if ((1543 < 2415) and (lL == "Stars")) then
                        for dX in pairs(lO) do
                            if (dX and dX["Parent"]) then
                                lV(dX)
                            end
                        end
                    elseif ((lL == "Particles") or (4444 < 2015)) then
                        for dX in pairs(lO) do
                            if (dX and dX["Parent"]) then
                                lW(dX)
                            end
                        end
                    elseif ((lL == "Smoke") or (4200 == 2332)) then
                        for dX in pairs(lO) do
                            if (dX and dX["Parent"]) then
                                lX(dX)
                            end
                        end
                    elseif (lL ~= "Lighting") then
                    else
                        for dX in pairs(lO) do
                            if ((dX and dX["Parent"]) or (1278 >= 1316)) then
                                lY(dX)
                            end
                        end
                    end
                end
            end
            f0.setMaterial = function(self, jX)
                lK = jX
                if iZ then
                    m0()
                end
            end
            f0.setAdd = function(self, jj)
                lL = jj
                if ((1082 == 1082) and iZ) then
                    for dX in pairs(lO) do
                        if (dX and dX["Parent"]) then
                            lR(dX)
                        end
                    end
                    if ((1328 <= 4878) and (jj == "Stars")) then
                        for dX in pairs(lO) do
                            if ((4087 >= 1355) and dX and dX["Parent"]) then
                                lV(dX)
                            end
                        end
                    elseif ((jj == "Particles") or (590 > 4650)) then
                        for dX in pairs(lO) do
                            if (dX and dX["Parent"]) then
                                lW(dX)
                            end
                        end
                    elseif (jj == "Smoke") then
                        for dX in pairs(lO) do
                            if ((dX and dX["Parent"]) or (3774 <= 3667)) then
                                lX(dX)
                            end
                        end
                    elseif (jj ~= "Lighting") then
                    else
                        for dX in pairs(lO) do
                            if ((1270 < 2146) and dX and dX["Parent"]) then
                                lY(dX)
                            end
                        end
                    end
                end
            end
            return f0
        end
    end,
    Visuals_Highlights = function()
        return function(dL)
            local f0 = {}
            local dN, ee, hf, wait = dL["lp"], dL["players"], dL["new"], dL["wait"]
            local m2, m3, m4, m5, m6 = false, false, nil, {}, {}
            local m7, m8, m9, ma = dL.c3rgb(255, 255, 255), 0.5, dL.c3rgb(0, 0, 0), 0
            local mb, mc, md, me = dL.c3rgb(255, 255, 255), 0.5, dL.c3rgb(0, 0, 0), 0
            local j3, mf, mg = nil, nil, nil
            local function mh()
                if not dN["Character"] then
                    return
                end
                if ((4563 >= 56) and m4) then
                    m4:Destroy()
                    m4 = nil
                end
                if (m2 or (446 == 622)) then
                    m4 = hf("Highlight")
                    m4["Adornee"], m4["FillColor"], m4["FillTransparency"] = dN["Character"], m7, m8
                    m4["OutlineColor"], m4["OutlineTransparency"] = m9, ma
                    m4["DepthMode"], m4["Parent"] = Enum["HighlightDepthMode"]["AlwaysOnTop"], dN["Character"]
                end
            end
            local function mi(eJ)
                if ((2069 > 1009) and (not eJ or (eJ == dN) or not eJ["Character"])) then
                    return
                end
                if m5[eJ] then
                    m5[eJ]:Destroy()
                    m5[eJ] = nil
                end
                if ((12 < 4208) and m3) then
                    local g8 = hf("Highlight")
                    g8["Adornee"], g8["FillColor"], g8["FillTransparency"] = eJ["Character"], mb, mc
                    g8["OutlineColor"], g8["OutlineTransparency"] = md, me
                    g8["DepthMode"], g8["Parent"] = Enum["HighlightDepthMode"]["AlwaysOnTop"], eJ["Character"]
                    m5[eJ] = g8
                end
            end
            local function mj()
                for D, eJ in pairs(ee:GetPlayers()) do
                    if (eJ == dN) then
                    else
                        mi(eJ)
                    end
                end
            end
            local function mk(eJ)
                if (m5[eJ] or (2990 <= 2980)) then
                    m5[eJ]:Destroy()
                    m5[eJ] = nil
                end
            end
            local function ml()
                for D, g8 in pairs(m5) do
                    g8:Destroy()
                end
                m5 = {}
            end
            f0.init = function(self)
                if dN["Character"] then
                    mh()
                end
            end
            local function mm()
                if (j3 or (2575 >= 4275)) then
                    return
                end
                j3 =
                    dN["CharacterAdded"]:Connect(
                    function()
                        wait(0.1)
                        mh()
                    end
                )
                mf =
                    ee["PlayerAdded"]:Connect(
                    function(eJ)
                        if (eJ == dN) then
                        else
                            m6[eJ] =
                                eJ["CharacterAdded"]:Connect(
                                function()
                                    wait(0.1)
                                    mi(eJ)
                                end
                            )
                        end
                    end
                )
                mg =
                    ee["PlayerRemoving"]:Connect(
                    function(eJ)
                        mk(eJ)
                        if (m6[eJ] or (3626 <= 1306)) then
                            m6[eJ]:Disconnect()
                            m6[eJ] = nil
                        end
                    end
                )
                for D, eJ in pairs(ee:GetPlayers()) do
                    if (eJ == dN) then
                    else
                        if eJ["Character"] then
                            mi(eJ)
                        end
                        m6[eJ] =
                            eJ["CharacterAdded"]:Connect(
                            function()
                                wait(0.1)
                                mi(eJ)
                            end
                        )
                    end
                end
            end
            local function mn()
                if j3 then
                    j3:Disconnect()
                    j3 = nil
                end
                if ((1368 < 3780) and mf) then
                    mf:Disconnect()
                    mf = nil
                end
                if (mg or (3169 == 2273)) then
                    mg:Disconnect()
                    mg = nil
                end
                for eJ, ju in pairs(m6) do
                    ju:Disconnect()
                    m6[eJ] = nil
                end
            end
            f0.setSelfEnable = function(self, jt)
                m2 = jt
                mh()
                if ((2481 <= 3279) and (jt or m3)) then
                    mm()
                elseif ((not jt and not m3) or (1063 <= 877)) then
                    mn()
                end
            end
            f0.setOthersEnable = function(self, jt)
                m3 = jt
                if ((2314 == 2314) and jt) then
                    mj()
                else
                    ml()
                end
                if (jt or m2) then
                    mm()
                elseif (not jt and not m2) then
                    mn()
                end
            end
            f0.setSelfFill = function(self, ju, jj)
                m7, m8 = ju, jj
                if m4 then
                    m4["FillColor"], m4["FillTransparency"] = ju, jj
                end
            end
            f0.setSelfOutline = function(self, ju, jj)
                m9, ma = ju, jj
                if ((924 >= 477) and m4) then
                    m4["OutlineColor"], m4["OutlineTransparency"] = ju, jj
                end
            end
            f0.setOthersFill = function(self, ju, jj)
                mb, mc = ju, jj
                for D, g8 in pairs(m5) do
                    g8["FillColor"], g8["FillTransparency"] = ju, jj
                end
            end
            f0.setOthersOutline = function(self, ju, jj)
                md, me = ju, jj
                for D, g8 in pairs(m5) do
                    g8["OutlineColor"], g8["OutlineTransparency"] = ju, jj
                end
            end
            return f0
        end
    end,
    Visuals_HitDetect = function()
        return function(dL)
            local f0 = {}
            local ee, dO, mo, mp = dL["players"], dL["heart"], dL["tweenservice"], dL["http"]
            local dN, e4, jv, mq = dL["lp"], dL["hooks"], dL["workspace"], dL["soundservice"]
            local ek, ie, ky = dL["insert"], dL["remove"], dL["find"]
            local fo, wait, jw = dL["spawn"], dL["wait"], dL["delay"]
            local iU, hf, el, kz = dL["c3rgb"], dL["new"], dL["floor"], dL["format"]
            local mr, ms = dL["gsub"], dL["match"]
            local eY, mt, mu, mv, mw = false, false, nil, {}, {}
            local mx, my, mz, mA, mB = false, iU(255, 0, 0), 0, 2, "Neon"
            local mC, mD, mE, mF = false, "skeet", 0.5, 1
            local mG, mH, mI = false, iU(255, 255, 255), "Dots"
            local mJ = {}
            local mK = nil
            local mL = {}
            local mM = {
                Neon = Enum["Material"]["Neon"],
                ForceField = Enum["Material"]["ForceField"],
                Glass = Enum["Material"]["Glass"]
            }
            local mN = {
                Head = true,
                UpperTorso = true,
                LowerTorso = true,
                LeftUpperArm = true,
                LeftLowerArm = true,
                LeftHand = true,
                RightUpperArm = true,
                RightLowerArm = true,
                RightHand = true,
                LeftUpperLeg = true,
                LeftLowerLeg = true,
                LeftFoot = true,
                RightUpperLeg = true,
                RightLowerLeg = true,
                RightFoot = true
            }
            local function j6(j7)
                local j8 = hf("ParticleEmitter")
                for j9, ja in pairs(j7) do
                    j8[j9] = ja
                end
                return j8
            end
            local mO, mP = {}, "intellect/Sounds"
            local function mQ(ec)
                local jV = mP .. "/" .. ec .. ".wav"
                if ((1813 <= 3778) and isfile(jV)) then
                    return
                end
                local mR, jM =
                    pcall(
                    game.HttpGet,
                    game,
                    "https://github.com/OnChangedCallback/sounds/raw/main/main/" .. ec .. ".wav"
                )
                if (mR and jM and (#jM > 0)) then
                    writefile(jV, jM)
                end
            end
            local function mS()
                if ((4150 == 4150) and not isfolder(mP)) then
                    return
                end
                local mT = listfiles(mP)
                for D, mU in ipairs(mT) do
                    if ((432 <= 3007) and ms(mU, "%.wav$")) then
                        local ec = mr(mU, ".*[\\/]", "")
                        ec = mr(ec, "%.wav$", "")
                        if (not ky(mO, ec) or (408 > 2721)) then
                            ek(mO, ec)
                        end
                    end
                end
            end
            local function mV()
                if not isfolder("intellect") then
                    makefolder("intellect")
                end
                if (not isfolder(mP) or (3418 < 2497)) then
                    makefolder(mP)
                end
                mS()
                fo(
                    function()
                        local mW = tick()
                        local bH = 10
                        local mX = false
                        fo(
                            function()
                                local mR, mY =
                                    pcall(
                                    game.HttpGet,
                                    game,
                                    "https://api.github.com/repos/OnChangedCallback/sounds/contents/main"
                                )
                                if mR then
                                    local mZ, jM = pcall(mp.JSONDecode, mp, mY)
                                    if ((1735 < 2169) and mZ and (type(jM) == "table")) then
                                        for D, mU in ipairs(jM) do
                                            if (mU["name"] and ms(mU.name, "%.wav$")) then
                                                local ec = mr(mU.name, "%.wav$", "")
                                                if ((3890 >= 3262) and not ky(mO, ec)) then
                                                    ek(mO, ec)
                                                end
                                                fo(mQ, ec)
                                            end
                                        end
                                    end
                                end
                                if (#mO ~= 0) then
                                else
                                    mO = {
                                        "bameware",
                                        "bonk",
                                        "bubble",
                                        "cod",
                                        "csgo",
                                        "fatality",
                                        "gamesense",
                                        "minecraft",
                                        "neverlose",
                                        "rust",
                                        "skeet",
                                        "tf2"
                                    }
                                    for D, ec in ipairs(mO) do
                                        fo(mQ, ec)
                                    end
                                end
                                mX = true
                            end
                        )
                        while not mX and ((tick() - mW) < bH) do
                            wait(0.1)
                        end
                        if not mX then
                            if ((#mO == 0) or (4356 >= 4649)) then
                                mO = {
                                    "bameware",
                                    "bonk",
                                    "bubble",
                                    "cod",
                                    "csgo",
                                    "fatality",
                                    "gamesense",
                                    "minecraft",
                                    "neverlose",
                                    "rust",
                                    "skeet",
                                    "tf2"
                                }
                            end
                            for D, ec in ipairs(mO) do
                                fo(mQ, ec)
                            end
                        end
                    end
                )
            end
            local function m_(ec, n0, n1)
                local jV = mP .. "/" .. ec .. ".wav"
                if not isfile(jV) then
                    return
                end
                local n2 = Instance.new("Sound")
                n2["Volume"] = n0
                n2["PlaybackSpeed"] = n1
                n2["SoundId"] = (getsynasset or getcustomasset)(jV)
                n2["Parent"] = mq
                n2:Play()
                n2["Ended"]:Connect(
                    function()
                        n2:Destroy()
                    end
                )
            end
            local function n3(dS)
                if ((3904 == 3904) and not (dS and dS:FindFirstChild("HumanoidRootPart"))) then
                    return
                end
                dS["Archivable"] = true
                local e9 = dS:Clone()
                e9["Name"], e9["Parent"] = "HitChams", jv
                local n4 = mM[mB] or Enum["Material"]["Neon"]
                local n5 = TweenInfo.new(mA, Enum["EasingStyle"].Sine, Enum["EasingDirection"].InOut)
                for D, eQ in ipairs(e9:GetChildren()) do
                    if ((eQ:IsA("BasePart") and mN[eQ["Name"]]) or (2860 >= 3789)) then
                        eQ["CanCollide"], eQ["CanQuery"], eQ["CanTouch"], eQ["Anchored"], eQ["Massless"] =
                            false,
                            false,
                            false,
                            true,
                            true
                        eQ["Transparency"], eQ["Color"], eQ["Material"] = mz, my, n4
                        mo:Create(eQ, n5, {Transparency = 1}):Play()
                    else
                        eQ:Destroy()
                    end
                end
                jw(
                    mA,
                    function()
                        if (e9["Parent"] or (1086 > 4449)) then
                            e9:Destroy()
                        end
                    end
                )
            end
            local function n6(dS)
                if not (dS and dS:FindFirstChild("HumanoidRootPart")) then
                    return
                end
                local ev = dS["HumanoidRootPart"]
                if ((4981 > 546) and (mI == "Dots")) then
                    local jj = hf("Attachment")
                    jj["Parent"] = ev
                    local i1 = {
                        LightEmission = 1,
                        Color = ColorSequence.new(mH),
                        LockedToPart = false,
                        ZOffset = 10,
                        Texture = "rbxassetid://7216849075",
                        VelocitySpread = 360,
                        Transparency = NumberSequence.new(
                            {NumberSequenceKeypoint.new(0, 0), NumberSequenceKeypoint.new(1, 0.663)}
                        ),
                        Lifetime = NumberRange.new(1, 5),
                        Speed = NumberRange.new(1, 210),
                        SpreadAngle = Vector2.new(360, -360),
                        Enable = false
                    }
                    local jk = j6(i1)
                    jk["Rate"] = 60
                    jk["Size"] =
                        NumberSequence.new(
                        {
                            NumberSequenceKeypoint.new(0, 0.1),
                            NumberSequenceKeypoint.new(0.428, 0),
                            NumberSequenceKeypoint.new(1, 0.627)
                        }
                    )
                    jk["Parent"] = jj
                    local jl = j6(i1)
                    jl["Rate"] = 100
                    jl["Size"] =
                        NumberSequence.new(
                        {
                            NumberSequenceKeypoint.new(0, 0.1),
                            NumberSequenceKeypoint.new(0.502, 1.438),
                            NumberSequenceKeypoint.new(0.925, 1.125),
                            NumberSequenceKeypoint.new(1, 0.397)
                        }
                    )
                    jl["Orientation"] = Enum["ParticleOrientation"]["FacingCamera"]
                    jl["Parent"] = jj
                    jk:Emit(60)
                    jl:Emit(100)
                    jw(
                        5,
                        function()
                            if (jj["Parent"] or (2366 <= 8)) then
                                jj:Destroy()
                            end
                        end
                    )
                elseif (mI == "Portal") then
                    local ey = ev["Position"]
                    local n7 = ey + Vector3.new(0, 50, 0)
                    local n8 = Vector3.new(0, -100, 0)
                    local n9 = RaycastParams.new()
                    n9["FilterType"] = Enum["RaycastFilterType"]["Blacklist"]
                    n9["FilterDescendantsInstances"] = {dS}
                    local na = jv:Raycast(n7, n8, n9)
                    local nb = (na and na["Position"]["Y"]) or (ey["Y"] - 3)
                    local nc = nb + 0.5
                    local nd = ey["Y"] + 10
                    local ne = Instance.new("Part")
                    ne["Name"] = "PortalEffect"
                    ne["CFrame"] = CFrame.new(ey.X, nc, ey.Z)
                    ne["BottomSurface"] = Enum["SurfaceType"]["Smooth"]
                    ne["Transparency"] = 1
                    ne["TopSurface"] = Enum["SurfaceType"]["Smooth"]
                    ne["Material"] = Enum["Material"]["SmoothPlastic"]
                    ne["Size"] = Vector3.new(1, 1, 1)
                    ne["Anchored"] = true
                    ne["CanCollide"] = false
                    ne["Parent"] = jv
                    local nf = Instance.new("Attachment")
                    nf["Name"] = "PortalBottom"
                    nf["CFrame"] = CFrame.new(0, 0, 0) * CFrame.Angles(math.rad(90), 0, 0)
                    nf["Parent"] = ne
                    local ng = Instance.new("Attachment")
                    ng["Name"] = "PortalTop"
                    ng["CFrame"] = CFrame.new(0, nd - nc, 0) * CFrame.Angles(math.rad(90), 0, 0)
                    ng["Parent"] = ne
                    local function nh(ni)
                        local kf = Instance.new("ParticleEmitter")
                        kf["Name"] = "PortalOutline"
                        kf["Lifetime"] = NumberRange.new(1, 1)
                        kf["SpreadAngle"] = Vector2.new(1, 1)
                        kf["LockedToPart"] = true
                        kf["Transparency"] =
                            NumberSequence.new(
                            {
                                NumberSequenceKeypoint.new(0, 1),
                                NumberSequenceKeypoint.new(0.0996264, 0),
                                NumberSequenceKeypoint.new(1, 0)
                            }
                        )
                        kf["LightEmission"] = 1
                        kf["Color"] = ColorSequence.new(mH)
                        kf["VelocitySpread"] = 1
                        kf["Speed"] = NumberRange.new(0.001, 0.001)
                        kf["ZOffset"] = 1
                        kf["Size"] = NumberSequence.new(0)
                        kf["RotSpeed"] = NumberRange.new(1000, 1000)
                        kf["Rate"] = 10
                        kf["Texture"] = "rbxassetid://16951115765"
                        kf["EmissionDirection"] = Enum["NormalId"]["Front"]
                        kf["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                        kf["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                        kf["Parent"] = ni
                        local nj = Instance.new("ParticleEmitter")
                        nj["Name"] = "Portal"
                        nj["Lifetime"] = NumberRange.new(1, 1)
                        nj["LockedToPart"] = true
                        nj["Transparency"] =
                            NumberSequence.new(
                            {
                                NumberSequenceKeypoint.new(0, 1),
                                NumberSequenceKeypoint.new(0.0996264, 0),
                                NumberSequenceKeypoint.new(1, 0)
                            }
                        )
                        nj["Color"] = ColorSequence.new(iU(0, 0, 0))
                        nj["Speed"] = NumberRange.new(0.001, 0.001)
                        nj["ZOffset"] = 0.5
                        nj["Size"] = NumberSequence.new(0)
                        nj["RotSpeed"] = NumberRange.new(1000, 1000)
                        nj["Rate"] = 5
                        nj["Texture"] = "rbxassetid://1084982817"
                        nj["EmissionDirection"] = Enum["NormalId"]["Front"]
                        nj["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                        nj["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                        nj["Parent"] = ni
                        local nk = Instance.new("ParticleEmitter")
                        nk["Name"] = "PortalSuck"
                        nk["Lifetime"] = NumberRange.new(1, 1)
                        nk["LockedToPart"] = true
                        nk["Transparency"] =
                            NumberSequence.new(
                            {
                                NumberSequenceKeypoint.new(0, 1),
                                NumberSequenceKeypoint.new(0.4993773, 0),
                                NumberSequenceKeypoint.new(1, 1)
                            }
                        )
                        nk["LightEmission"] = 1
                        nk["Color"] = ColorSequence.new(mH)
                        nk["Speed"] = NumberRange.new(0.001, 0.001)
                        nk["Brightness"] = 10
                        nk["Size"] = NumberSequence.new(0)
                        nk["RotSpeed"] = NumberRange.new(500, 500)
                        nk["Rate"] = 4
                        nk["Texture"] = "rbxassetid://16951208736"
                        nk["EmissionDirection"] = Enum["NormalId"]["Front"]
                        nk["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                        nk["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                        nk["Parent"] = ni
                        return kf, nj, nk
                    end
                    local nl, nm, nn = nh(nf)
                    local no, np, nq = nh(ng)
                    local nr = Instance.new("ParticleEmitter")
                    nr["Name"] = "PortalLines"
                    nr["Lifetime"] = NumberRange.new(0.5, 0.5)
                    nr["SpreadAngle"] = Vector2.new(80, 80)
                    nr["LockedToPart"] = true
                    nr["Transparency"] =
                        NumberSequence.new(
                        {
                            NumberSequenceKeypoint.new(0, 1),
                            NumberSequenceKeypoint.new(0.1976503, 1),
                            NumberSequenceKeypoint.new(0.5003455, 0),
                            NumberSequenceKeypoint.new(0.7988943, 1),
                            NumberSequenceKeypoint.new(1, 1)
                        }
                    )
                    nr["LightEmission"] = 1
                    nr["Color"] = ColorSequence.new(mH)
                    nr["VelocitySpread"] = 80
                    nr["Squash"] = NumberSequence.new(0.5)
                    nr["Speed"] = NumberRange.new(15, 15)
                    nr["ZOffset"] = 1
                    nr["Size"] = NumberSequence.new(2.330097, 0)
                    nr["ShapeInOut"] = Enum["ParticleEmitterShapeInOut"]["Inward"]
                    nr["Rate"] = 50
                    nr["Texture"] = "rbxassetid://16953209220"
                    nr["EmissionDirection"] = Enum["NormalId"]["Front"]
                    nr["Orientation"] = Enum["ParticleOrientation"]["VelocityParallel"]
                    nr["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                    nr["Rotation"] = NumberRange.new(-90, -90)
                    nr["Enable"] = false
                    nr["Parent"] = ng
                    local ns = Instance.new("Beam")
                    ns["FaceCamera"] = true
                    ns["LightInfluence"] = 1
                    ns["TextureSpeed"] = 10
                    ns["Width1"] = 6.5
                    ns["Width0"] = 6.5
                    ns["Transparency"] = NumberSequence.new(1)
                    ns["LightEmission"] = 1
                    ns["Color"] = ColorSequence.new(mH)
                    ns["Texture"] = "rbxassetid://2316283203"
                    ns["Attachment0"] = ng
                    ns["Attachment1"] = nf
                    ns["Parent"] = ng
                    local nt = Instance.new("Beam")
                    nt["FaceCamera"] = true
                    nt["LightInfluence"] = 1
                    nt["TextureSpeed"] = 10
                    nt["Width1"] = 6.5
                    nt["Width0"] = 6.5
                    nt["Transparency"] = NumberSequence.new(1)
                    nt["LightEmission"] = 1
                    nt["Color"] = ColorSequence.new(mH)
                    nt["Texture"] = "rbxassetid://2316283203"
                    nt["Attachment0"] = ng
                    nt["Attachment1"] = nf
                    nt["Parent"] = ng
                    fo(
                        function()
                            local nu = 0.3
                            local nv = 0.5
                            local nw = 0.3
                            local mW = tick()
                            while (tick() - mW) < nu do
                                local jx = (tick() - mW) / nu
                                nl["Size"] = NumberSequence.new(3 * jx)
                                nm["Size"] = NumberSequence.new(2 * jx)
                                nn["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 5.4854369 * jx),
                                        NumberSequenceKeypoint.new(1, 2.0873785 * jx)
                                    }
                                )
                                no["Size"] = NumberSequence.new(3 * jx)
                                np["Size"] = NumberSequence.new(2 * jx)
                                nq["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 5.4854369 * jx),
                                        NumberSequenceKeypoint.new(1, 2.0873785 * jx)
                                    }
                                )
                                wait()
                            end
                            nl["Size"] = NumberSequence.new(3)
                            nm["Size"] = NumberSequence.new(2)
                            nn["Size"] =
                                NumberSequence.new(
                                {NumberSequenceKeypoint.new(0, 5.4854369), NumberSequenceKeypoint.new(1, 2.0873785)}
                            )
                            no["Size"] = NumberSequence.new(3)
                            np["Size"] = NumberSequence.new(2)
                            nq["Size"] =
                                NumberSequence.new(
                                {NumberSequenceKeypoint.new(0, 5.4854369), NumberSequenceKeypoint.new(1, 2.0873785)}
                            )
                            nr["Enable"] = true
                            mW = tick()
                            while (tick() - mW) < nv do
                                local jx = (tick() - mW) / nv
                                ns["Transparency"] = NumberSequence.new(1 - jx)
                                nt["Transparency"] = NumberSequence.new(1 - jx)
                                wait()
                            end
                            ns["Transparency"] = NumberSequence.new(0)
                            nt["Transparency"] = NumberSequence.new(0)
                            wait(0.5)
                            mW = tick()
                            while (tick() - mW) < nv do
                                local jx = (tick() - mW) / nv
                                ns["Transparency"] = NumberSequence.new(jx)
                                nt["Transparency"] = NumberSequence.new(jx)
                                wait()
                            end
                            ns["Transparency"] = NumberSequence.new(1)
                            nt["Transparency"] = NumberSequence.new(1)
                            nr["Enable"] = false
                            mW = tick()
                            while (tick() - mW) < nw do
                                local jx = 1 - ((tick() - mW) / nw)
                                nl["Size"] = NumberSequence.new(3 * jx)
                                nm["Size"] = NumberSequence.new(2 * jx)
                                nn["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 5.4854369 * jx),
                                        NumberSequenceKeypoint.new(1, 2.0873785 * jx)
                                    }
                                )
                                no["Size"] = NumberSequence.new(3 * jx)
                                np["Size"] = NumberSequence.new(2 * jx)
                                nq["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 5.4854369 * jx),
                                        NumberSequenceKeypoint.new(1, 2.0873785 * jx)
                                    }
                                )
                                wait()
                            end
                            if ne["Parent"] then
                                ne:Destroy()
                            end
                        end
                    )
                elseif ((mI == "Fortnite") or (2590 == 2864)) then
                    local dT = dS:FindFirstChildOfClass("Humanoid")
                    if (not dT or (2624 > 4149)) then
                        return
                    end
                    local nx = el(dT.Health)
                    local ny = el(dT.MaxHealth)
                    local nz = ny - nx
                    if (nz > 0) then
                    else
                        return
                    end
                    local nA = mJ[dS]
                    if ((nA and nA["billboard"] and nA["billboard"]["Parent"]) or (2618 >= 4495)) then
                        nA["totalDamage"] = nA["totalDamage"] + nz
                        nA["label"]["Text"] = "-" .. nA["totalDamage"]
                        nA["startTime"] = tick()
                        nA["billboard"]["StudsOffset"] = Vector3.new(0, 3, 0)
                        nA["label"]["TextTransparency"] = 0
                        nA["label"]["TextStrokeTransparency"] = 0
                    else
                        local nB = Instance.new("BillboardGui")
                        nB["Name"] = "DamageIndicator"
                        nB["Size"] = UDim2.new(0, 100, 0, 50)
                        nB["StudsOffset"] = Vector3.new(0, 3, 0)
                        nB["AlwaysOnTop"] = true
                        nB["ZIndexBehavior"] = Enum["ZIndexBehavior"]["Sibling"]
                        nB["Parent"] = ev
                        local aQ = Instance.new("TextLabel")
                        aQ["Size"] = UDim2.new(1, 0, 1, 0)
                        aQ["BorderSizePixel"] = 0
                        aQ["BackgroundTransparency"] = 1
                        aQ["FontSize"] = Enum["FontSize"]["Size48"]
                        aQ["TextStrokeTransparency"] = 0
                        aQ["TextSize"] = 38
                        aQ["TextColor3"] = mH
                        aQ["Text"] = "-" .. nz
                        aQ["Font"] = Enum["Font"]["LuckiestGuy"]
                        aQ["ZIndex"] = 999999
                        aQ["Parent"] = nB
                        local nC = {billboard = nB, label = aQ, totalDamage = nz, startTime = tick()}
                        mJ[dS] = nC
                        fo(
                            function()
                                local nD = 1.5
                                local nE = Vector3.new(0, 3, 0)
                                local nF = Vector3.new(0, 5, 0)
                                while nB["Parent"] do
                                    local nG = tick() - nC["startTime"]
                                    if (nG >= nD) then
                                        break
                                    end
                                    local jx = nG / nD
                                    nB["StudsOffset"] = nE:Lerp(nF, jx)
                                    aQ["TextTransparency"] = jx
                                    aQ["TextStrokeTransparency"] = jx
                                    wait()
                                end
                                if (nB["Parent"] or (2485 >= 3131)) then
                                    nB:Destroy()
                                end
                                mJ[dS] = nil
                            end
                        )
                    end
                elseif ((mI == "Explode") or (2804 <= 2785)) then
                    local nH = Instance.new("Explosion")
                    nH["Position"] = ev["Position"]
                    nH["BlastRadius"] = 10
                    nH["BlastPressure"] = 0
                    nH["DestroyJointRadiusPercent"] = 0
                    nH["ExplosionType"] = Enum["ExplosionType"]["NoCraters"]
                    nH["Parent"] = jv
                    fo(
                        function()
                            wait(2)
                            if nH["Parent"] then
                                nH:Destroy()
                            end
                        end
                    )
                end
            end
            local function nI(nJ, nK)
                if (mx or (4571 == 3415)) then
                    pcall(n3, nJ.char)
                end
                if mC then
                    pcall(m_, mD, mE, mF)
                end
                if mG then
                    pcall(n6, nJ.char)
                end
                if (mt or (4441 > 4787)) then
                    fo(
                        function()
                            local dT = nJ["char"]:FindFirstChildOfClass("Humanoid")
                            local nL = {}
                            if ((1920 == 1920) and mw["Nickname"] and mw["DisplayName"]) then
                                ek(nL, kz("Hit %s(%s)", nK.DisplayName, nK.Name))
                            elseif (mw["DisplayName"] or (647 == 4477)) then
                                ek(nL, "Hit " .. nK["DisplayName"])
                            elseif ((3819 == 3819) and mw["Nickname"]) then
                                ek(nL, "Hit " .. nK["Name"])
                            else
                                ek(nL, "Hit")
                            end
                            if mw["HitPart"] then
                                ek(nL, "in " .. nJ["part"])
                            end
                            if ((mw["LastHP"] and dT) or (1466 > 4360)) then
                                ek(nL, kz("(%d/%d)", el(dT.Health), el(dT.MaxHealth)))
                            end
                            if (mw["Distance"] or (14 > 994)) then
                                ek(nL, kz("[%dm]", el((nJ["spos"] - nJ["epos"])["Magnitude"] * 0.28)))
                            end
                            mu:Notify(table.concat(nL, " "), 2)
                        end
                    )
                end
            end
            local function nM(ea)
                if ((401 <= 734) and (ea[1] == "ShootGun") and eY) then
                    local ho = ea[5]
                    if (ho and ho["Parent"]) then
                        ek(mv, {char = ho["Parent"], part = ho["Name"], spos = ea[3], epos = ea[4]})
                    end
                end
            end
            local function nN()
                if (not eY or (#mv == 0) or not mu or (2167 >= 3426)) then
                    return
                end
                while #mv > 0 do
                    local nJ = ie(mv, 1)
                    if nJ["char"] then
                        local nK = nil
                        for D, eJ in pairs(ee:GetPlayers()) do
                            if ((eJ["Character"] == nJ["char"]) and (eJ ~= dN)) then
                                nK = eJ
                                break
                            end
                        end
                        if ((764 < 3285) and nK) then
                            local dT = nJ["char"]:FindFirstChildOfClass("Humanoid")
                            if (dT and not mL[dT]) then
                                local bH = tick() + 0.5
                                local nO = dT["Health"]
                                local k1 = nil
                                k1 =
                                    dT:GetPropertyChangedSignal("Health"):Connect(
                                    function()
                                        local nx = dT["Health"]
                                        if ((2499 == 2499) and (tick() > bH)) then
                                            if k1 then
                                                k1:Disconnect()
                                            end
                                            mL[dT] = nil
                                            return
                                        end
                                        if (nx < nO) then
                                        else
                                            nO = nx
                                            return
                                        end
                                        if k1 then
                                            k1:Disconnect()
                                        end
                                        mL[dT] = nil
                                        nI(nJ, nK)
                                    end
                                )
                                mL[dT] = {conn = k1, timeout = bH, hit = nJ, plr = nK, previousHP = nO}
                                fo(
                                    function()
                                        wait(0.5)
                                        if ((mL[dT] and (mL[dT]["conn"] == k1)) or (692 >= 4933)) then
                                            k1:Disconnect()
                                            mL[dT] = nil
                                        end
                                    end
                                )
                            end
                        end
                    end
                end
            end
            f0.init = function(self, nP)
                mu = nP
                mV()
                e4:register("HitDetect", nM)
            end
            local function nQ()
                if (mK or (3154 <= 2260)) then
                    return
                end
                mK =
                    dO:Connect(
                    (
                        newcclosure(
                            function()
                                nN()
                            end
                        )
                    )
                )
            end
            local function nR()
                if (mK or (2637 > 3149)) then
                    mK:Disconnect()
                    mK = nil
                end
            end
            f0.getSounds = function(self)
                return mO
            end
            f0.setEnable = function(self, dR)
                eY = dR
                if (dR or (3992 < 2407)) then
                    nQ()
                else
                    nR()
                end
            end
            f0.setNotify = function(self, dR)
                mt = dR
            end
            f0.setNotifyOptions = function(self, nS)
                mw = nS
            end
            f0.setChams = function(self, dR)
                mx = dR
            end
            f0.setChamsColor = function(self, hP, jx)
                my, mz = hP, jx or 0
            end
            f0.setChamsMaterial = function(self, n4)
                mB = n4
            end
            f0.setChamsLifetime = function(self, nT)
                mA = nT
            end
            f0.setSound = function(self, dR)
                mC = dR
            end
            f0.setSoundName = function(self, ec)
                mD = ec
            end
            f0.setSoundVolume = function(self, n0)
                mE = n0
            end
            f0.setSoundPitch = function(self, n1)
                mF = n1
            end
            f0.setEffects = function(self, dR)
                mG = dR
            end
            f0.setEffectsColor = function(self, hP)
                mH = hP
            end
            f0.setEffectsType = function(self, nU)
                mI = nU
            end
            return f0
        end
    end,
    Visuals_SelfChams = function()
        return function(dL)
            local f0 = {}
            local dN, hf, iU = dL["lp"], dL["new"], dL["c3rgb"]
            local hT, kw = dL["min"], dL["max"]
            local iZ, j0, jx, lK = false, iU(155, 125, 175), 0, "ForceField"
            local lL, lM, lN = "None", iU(255, 255, 255), 0
            local j3 = nil
            local nV = {
                "LeftFoot",
                "LeftLowerLeg",
                "LeftUpperLeg",
                "RightFoot",
                "RightLowerLeg",
                "RightUpperLeg",
                "LeftHand",
                "LeftLowerArm",
                "LeftUpperArm",
                "RightHand",
                "RightLowerArm",
                "RightUpperArm",
                "LowerTorso",
                "UpperTorso",
                "Head"
            }
            local function nW(nX)
                for w = 1, #nV do
                    if ((nV[w] == nX) or (2902 > 4859)) then
                        return true
                    end
                end
                return false
            end
            local function lR()
                if ((1679 < 4359) and not dN["Character"]) then
                    return
                end
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if ((1913 < 4670) and nW(eJ.Name)) then
                        local jt = eJ:FindFirstChild("stars")
                        if jt then
                            jt:Destroy()
                        end
                        local lS = eJ:FindFirstChild("Specks")
                        if lS then
                            lS:Destroy()
                        end
                        local lT = eJ:FindFirstChild("Smoke1")
                        if lT then
                            lT:Destroy()
                        end
                        local lU = eJ:FindFirstChild("Lighting")
                        if lU then
                            lU:Destroy()
                        end
                    end
                end
            end
            local function lV()
                if not dN["Character"] then
                    return
                end
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if (nW(eJ.Name) and eJ:IsA("BasePart")) then
                        local j8 = eJ:FindFirstChild("stars")
                        if j8 then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local jt = hf("ParticleEmitter")
                                jt["Name"] = "stars"
                                jt["FlipbookFramerate"] = NumberRange.new(16, 16)
                                jt["Lifetime"] = NumberRange.new(0.45, 0.9)
                                jt["LockedToPart"] = true
                                jt["LightEmission"] = 1
                                jt["Drag"] = 5
                                jt["Squash"] = NumberSequence.new(-0.1)
                                jt["Speed"] = NumberRange.new(0.001, 0.001)
                                jt["Brightness"] = 3
                                jt["ZOffset"] = 1
                                jt["Size"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, 0),
                                        NumberSequenceKeypoint.new(0.508, 0.05, 0.05),
                                        NumberSequenceKeypoint.new(1, 0)
                                    }
                                )
                                jt["Rate"] = 150
                                jt["Texture"] = "rbxassetid://1084996976"
                                jt["EmissionDirection"] = Enum["NormalId"]["Bottom"]
                                jt["Color"] = ColorSequence.new(lM)
                                jt["Transparency"] = NumberSequence.new(lN)
                                jt["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lW()
                if not dN["Character"] then
                    return
                end
                for D, eJ in pairs(dN["Characer"]:GetChildren()) do
                    if ((nW(eJ.Name) and eJ:IsA("BasePart")) or (2846 < 879)) then
                        local j8 = eJ:FindFirstChild("Specks")
                        if j8 then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lS = hf("ParticleEmitter")
                                lS["Name"] = "Specks"
                                lS["Lifetime"] = NumberRange.new(0.22, 0.22)
                                lS["SpreadAngle"] = Vector2.new(90, 90)
                                lS["Transparency"] =
                                    NumberSequence.new(
                                    {
                                        NumberSequenceKeypoint.new(0, hT(1, lN + 0.8)),
                                        NumberSequenceKeypoint.new(0.25, kw(0, lN - 0.1)),
                                        NumberSequenceKeypoint.new(1, hT(1, lN + 0.8))
                                    }
                                )
                                lS["LightEmission"] = 1
                                lS["Color"] = ColorSequence.new(lM)
                                lS["Drag"] = 5
                                lS["VelocitySpread"] = 90
                                lS["Squash"] = NumberSequence.new(0)
                                lS["Speed"] = NumberRange.new(1, 1)
                                lS["Brightness"] = 4.2
                                lS["Size"] = NumberSequence.new(0.15)
                                lS["Acceleration"] = Vector3.new(0, -15, 0)
                                lS["RotSpeed"] = NumberRange.new(-45, 45)
                                lS["ShapeInOut"] = Enum["ParticleEmitterShapeInOut"]["InAndOut"]
                                lS["Rate"] = 100
                                lS["Texture"] = "rbxassetid://7216849703"
                                lS["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lX()
                if ((4588 == 4588) and not dN["Character"]) then
                    return
                end
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if (nW(eJ.Name) and eJ:IsA("BasePart")) then
                        local j8 = eJ:FindFirstChild("Smoke1")
                        if (j8 or (347 == 2065)) then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lT = hf("ParticleEmitter")
                                lT["Name"] = "Smoke1"
                                lT["Lifetime"] = NumberRange.new(0.8, 0.8)
                                lT["FlipbookLayout"] = Enum["ParticleFlipbookLayout"]["Grid4x4"]
                                lT["SpreadAngle"] = Vector2.new(0, 360)
                                lT["LockedToPart"] = true
                                lT["Transparency"] = NumberSequence.new(lN)
                                lT["LightEmission"] = 0.5
                                lT["Color"] = ColorSequence.new(lM)
                                lT["Speed"] = NumberRange.new(0, 0)
                                lT["ZOffset"] = 2
                                lT["RotSpeed"] = NumberRange.new(-50, 50)
                                lT["Rate"] = 5
                                lT["Texture"] = "rbxassetid://14006773822"
                                lT["EmissionDirection"] = Enum["NormalId"]["Front"]
                                lT["Orientation"] = Enum["ParticleOrientation"]["FacingCameraWorldUp"]
                                lT["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                                lT["Rotation"] = NumberRange.new(-360, 360)
                                lT["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lY()
                if (not dN["Character"] or (1311 > 2697)) then
                    return
                end
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if ((nW(eJ.Name) and eJ:IsA("BasePart")) or (2717 > 3795)) then
                        local j8 = eJ:FindFirstChild("Lighting")
                        if (j8 or (1081 < 391)) then
                            j8:Destroy()
                        end
                        pcall(
                            function()
                                local lU = hf("ParticleEmitter")
                                lU["Name"] = "Lighting"
                                lU["FlipbookFramerate"] = NumberRange.new(40, 70)
                                lU["Lifetime"] = NumberRange.new(0.5, 1)
                                lU["FlipbookLayout"] = Enum["ParticleFlipbookLayout"]["Grid4x4"]
                                lU["SpreadAngle"] = Vector2.new(360, 360)
                                lU["LockedToPart"] = true
                                lU["Transparency"] = NumberSequence.new(lN)
                                lU["LightEmission"] = -1
                                lU["Color"] = ColorSequence.new(lM)
                                lU["Drag"] = 8
                                lU["VelocitySpread"] = 360
                                lU["Speed"] = NumberRange.new(0.0006561, 0.0006561)
                                lU["Brightness"] = 20
                                lU["ZOffset"] = 1
                                lU["Size"] = NumberSequence.new(0.852325)
                                lU["Rate"] = 5
                                lU["Texture"] = "rbxassetid://17005524119"
                                lU["Orientation"] = Enum["ParticleOrientation"]["VelocityPerpendicular"]
                                lU["FlipbookMode"] = Enum["ParticleFlipbookMode"]["OneShot"]
                                lU["Rotation"] = NumberRange.new(-360, 360)
                                lU["Parent"] = eJ
                            end
                        )
                    end
                end
            end
            local function lZ()
                if (not iZ or not dN["Character"] or (121 > 3438)) then
                    return
                end
                for D, ja in pairs(dN["Character"]:GetChildren()) do
                    if (ja:IsA("Pants") or ja:IsA("Shirt")) then
                        ja:Destroy()
                    end
                end
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if ((71 < 1949) and nW(eJ.Name) and eJ:IsA("BasePart")) then
                        eJ["Material"], eJ["Color"], eJ["Transparency"] = Enum["Material"][lK], j0, jx
                        if ((4254 == 4254) and eJ:IsA("MeshPart")) then
                            eJ["TextureID"] = ""
                        end
                    end
                end
                if ((3196 >= 2550) and (lL == "Stars")) then
                    lV()
                elseif ((2456 < 4176) and (lL == "Particles")) then
                    lW()
                elseif (lL == "Smoke") then
                    lX()
                elseif (lL == "Lighting") then
                    lY()
                else
                    lR()
                end
            end
            local function l_()
                if (not dN["Character"] or (1150 == 3452)) then
                    return
                end
                lR()
                for D, eJ in pairs(dN["Character"]:GetChildren()) do
                    if ((1875 < 2258) and nW(eJ.Name) and eJ:IsA("BasePart")) then
                        eJ["Material"] = Enum["Material"]["Plastic"]
                        eJ["Transparency"] = 0
                    end
                end
            end
            f0.init = function(self)
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                if jt then
                    if not j3 then
                        j3 =
                            dN["CharacterAdded"]:Connect(
                            function(dS)
                                if ((1173 > 41) and iZ) then
                                    dS:WaitForChild("Humanoid")
                                    dL.wait(0.1)
                                    lZ()
                                end
                            end
                        )
                    end
                    lZ()
                else
                    if (j3 or (56 >= 3208)) then
                        j3:Disconnect()
                        j3 = nil
                    end
                    l_()
                end
            end
            f0.setColor = function(self, ju, jj)
                j0, jx = ju, jj
                if iZ then
                    lZ()
                end
            end
            f0.setParticleColor = function(self, ju, jj)
                lM, lN = ju, jj
                if ((4313 > 3373) and iZ) then
                    if (lL == "Stars") then
                        lV()
                    elseif ((lL == "Particles") or (4493 == 2225)) then
                        lW()
                    elseif (lL == "Smoke") then
                        lX()
                    elseif (lL ~= "Lighting") then
                    else
                        lY()
                    end
                end
            end
            f0.setMaterial = function(self, jX)
                lK = jX
                if iZ then
                    lZ()
                end
            end
            f0.setAdd = function(self, jj)
                lL = jj
                if iZ then
                    lR()
                    if ((3104 >= 3092) and (jj == "Stars")) then
                        lV()
                    elseif ((3548 > 3098) and (jj == "Particles")) then
                        lW()
                    elseif ((jj == "Smoke") or (3252 == 503)) then
                        lX()
                    elseif (jj ~= "Lighting") then
                    else
                        lY()
                    end
                end
            end
            return f0
        end
    end,
    Visuals_Textures = function()
        return function(dL)
            local f0, hf, dO, iZ, nY, k1 = {}, dL["new"], dL["heart"], false, {}, nil
            local nZ = {"Front", "Back", "Bottom", "Top", "Right", "Left"}
            local n_ = {
                Wood = "128754006217410",
                WoodPlanks = "5625184464",
                Brick = "8139086777",
                Cobblestone = "17874801808",
                Concrete = "15622710576",
                DiamondPlate = "14197861013",
                Fabric = "9744916443",
                Granite = "4714662147",
                Grass = "9267183930",
                Ice = "11413423466",
                Marble = "14974016515",
                Metal = "12623531687",
                Sand = "11119324718",
                Slate = "8139086777",
                Ground = "9267089500"
            }
            local function lL(eJ, o0)
                if ((4733 > 2066) and nY[eJ]) then
                    return
                end
                for D, a in pairs(nZ) do
                    local dX = hf("Texture")
                    dX["Name"],
                        dX["ZIndex"],
                        dX["Texture"],
                        dX["Face"],
                        dX["Color3"],
                        dX["Transparency"],
                        dX["StudsPerTileU"],
                        dX["StudsPerTileV"],
                        dX["Parent"] =
                        "UnnamedTex",
                        2147483647,
                        "rbxassetid://" .. o0,
                        Enum["NormalId"][a],
                        eJ["Color"],
                        eJ["Transparency"],
                        4,
                        4,
                        eJ
                end
                nY[eJ] = true
            end
            local function lZ(o1, aZ)
                for D, eJ in pairs(o1:GetChildren()) do
                    if ((3549 >= 916) and iZ and eJ:IsA("BasePart")) then
                        local jX = eJ["Material"]["Name"]
                        if (n_[jX] or (2189 <= 245)) then
                            lL(eJ, n_[jX])
                            eJ["Material"] = Enum["Material"]["SmoothPlastic"]
                            aZ[1] = aZ[1] + 1
                            if (aZ[1] < 400) then
                            else
                                aZ[1] = 0
                                dO:Wait()
                            end
                        end
                    end
                    lZ(eJ, aZ)
                end
            end
            local function o2(o1, aZ)
                for D, o3 in pairs(o1:GetChildren()) do
                    if ((o3:IsA("Texture") and (o3["Name"] == "UnnamedTex")) or (1389 > 3925)) then
                        o3:Destroy()
                        aZ[1] = aZ[1] + 1
                        if (aZ[1] < 800) then
                        else
                            aZ[1] = 0
                            dO:Wait()
                        end
                    end
                    o2(o3, aZ)
                end
            end
            local function jr()
                if k1 then
                    k1:Disconnect()
                    k1 = nil
                end
                if ((4169 >= 3081) and iZ) then
                    dL.spawn(
                        function()
                            lZ(dL.workspace, {0})
                        end
                    )
                    k1 =
                        dL["workspace"]["DescendantAdded"]:Connect(
                        function(o4)
                            if (iZ and o4:IsA("BasePart")) then
                                local jX = o4["Material"]["Name"]
                                if ((349 <= 894) and n_[jX]) then
                                    lL(o4, n_[jX])
                                    o4["Material"] = Enum["Material"]["SmoothPlastic"]
                                end
                            end
                        end
                    )
                else
                    dL.spawn(
                        function()
                            o2(dL.workspace, {0})
                            nY = {}
                        end
                    )
                end
            end
            f0.init = function(self)
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                jr()
            end
            f0.setType = function(self, dX)
            end
            return f0
        end
    end,
    Visuals_Weather = function()
        return function(dL)
            local f0 = {}
            local dN, hf, fo, wait, ej, f2, dQ, iV, iW, iX, iY, he =
                dL["lp"],
                dL["new"],
                dL["spawn"],
                dL["wait"],
                dL["v2"],
                dL["v3"],
                dL["cf"],
                dL["nr"],
                dL["ns"],
                dL["nsk"],
                dL["cs"],
                dL["c3rgb"]
            local iZ, o5, j0, ho, j2, j3 = false, "Rain", he(255, 255, 255), nil, {}, nil
            local function j6(eJ)
                local j8 = hf("ParticleEmitter")
                for j9, ja in pairs(eJ) do
                    j8[j9] = ja
                end
                j2[#j2 + 1] = j8
                return j8
            end
            local function o6()
                local g8 = dN["Character"] and dN["Character"]:FindFirstChild("Head")
                if not g8 then
                    return
                end
                ho = hf("Part")
                ho["Size"],
                    ho["Transparency"],
                    ho["CanCollide"],
                    ho["CanQuery"],
                    ho["CanTouch"],
                    ho["Anchored"],
                    ho["Massless"],
                    ho["Parent"] = f2(300, 300, 300), 1, false, false, false, false, true, dL["workspace"]
                local o7 = hf("Weld")
                o7["Part0"], o7["Part1"], o7["Parent"] = g8, ho, ho
            end
            local i_ = {
                Rain = function()
                    local dX, jY, jt, o4, o3 =
                        "http://www.roblox.com/asset/?id=3806148993",
                        iV(2.5, 2.5),
                        iV(200, 200),
                        Enum["NormalId"]["Bottom"],
                        Enum["ParticleOrientation"]["FacingCameraWorldUp"]
                    j6(
                        {
                            Lifetime = jY,
                            Transparency = iW(0.5),
                            Color = iY(j0),
                            Speed = jt,
                            Size = iW(5),
                            Rate = 15000,
                            Texture = dX,
                            EmissionDirection = o4,
                            Rotation = iV(-1, 1),
                            Parent = ho
                        }
                    )
                    j6(
                        {
                            Lifetime = jY,
                            Transparency = iW({iX(0, 0.571), iX(1, 0.416)}),
                            Color = iY(j0),
                            Squash = iW({iX(0, 0.5), iX(1, 3)}),
                            Speed = jt,
                            Size = iW(3),
                            Rate = 10000,
                            Texture = dX,
                            EmissionDirection = o4,
                            Orientation = o3,
                            Parent = ho
                        }
                    )
                    j6(
                        {
                            Lifetime = jY,
                            Transparency = iW({iX(0, 0.733), iX(1, 0.398)}),
                            Color = iY(j0),
                            Speed = jt,
                            Size = iW(3),
                            Rate = 15000,
                            Texture = dX,
                            EmissionDirection = o4,
                            Orientation = o3,
                            Rotation = iV(-1, 1),
                            Parent = ho
                        }
                    )
                    j6(
                        {
                            Lifetime = jY,
                            Transparency = iW({iX(0, 0.503), iX(1, 0.435)}),
                            Color = iY(j0),
                            Speed = jt,
                            Size = iW(3),
                            Rate = 15000,
                            Texture = dX,
                            EmissionDirection = o4,
                            Orientation = o3,
                            Rotation = iV(-1, 1),
                            Parent = ho
                        }
                    )
                end,
                Snow = function()
                    j6(
                        {
                            SpreadAngle = ej(50, 50),
                            Transparency = iW({iX(0, 0), iX(0.984, 0.044), iX(1, 1)}),
                            Color = iY(j0),
                            LightEmission = 0.5,
                            VelocitySpread = 50,
                            Speed = iV(15, 15),
                            Size = iW({iX(0, 0.331), iX(0.551, 0.402), iX(1, 0.331)}),
                            Rate = 500,
                            Texture = "rbxassetid://917186750",
                            EmissionDirection = Enum["NormalId"]["Bottom"],
                            Parent = ho
                        }
                    )
                end,
                Autumn = function()
                    j6(
                        {
                            SpreadAngle = ej(50, 50),
                            Transparency = iW({iX(0, 0), iX(0.984, 0.044), iX(1, 1)}),
                            Color = iY(j0),
                            LightEmission = 0.75,
                            VelocitySpread = 50,
                            Speed = iV(30, 30),
                            Size = iW(0.8),
                            Rate = 1000,
                            Texture = "rbxassetid://915916073",
                            Orientation = Enum["ParticleOrientation"]["VelocityPerpendicular"],
                            EmissionDirection = Enum["NormalId"]["Bottom"],
                            Parent = ho
                        }
                    )
                end
            }
            local function jr()
                if (ho and ho["Parent"]) then
                    ho:Destroy()
                end
                ho, j2 = nil, {}
                if ((731 <= 2978) and iZ) then
                    o6()
                    if ((ho and i_[o5]) or (892 > 3892)) then
                        i_[o5]()
                    end
                end
            end
            f0.init = function(self)
                if (dN["Character"] and iZ) then
                    fo(
                        function()
                            wait(0.5)
                            jr()
                        end
                    )
                end
            end
            f0.setEnable = function(self, jt)
                iZ = jt
                if jt then
                    if not j3 then
                        j3 =
                            dN["CharacterAdded"]:Connect(
                            function()
                                if (iZ or (4466 == 900)) then
                                    wait(0.5)
                                    jr()
                                end
                            end
                        )
                    end
                elseif (j3 or (2084 >= 2888)) then
                    j3:Disconnect()
                    j3 = nil
                end
                jr()
            end
            f0.setType = function(self, dX)
                o5 = dX
                jr()
            end
            f0.setColor = function(self, ju)
                j0 = ju
                for w = 1, #j2 do
                    if (j2[w] and j2[w]["Parent"]) then
                        j2[w]["Color"] = iY(j0)
                    end
                end
            end
            return f0
        end
    end,









    ConfigManager = function()
        local mp = cloneref(game:GetService("HttpService"))
        local o8 = {}
        do
            o8["folder"] = "intellectSettings"
            o8["ignore"] = {}
            o8["parser"] = {
                Toggle = {
                    Save = function(o9, e_)
                        return {type = "Toggle", idx = o9, value = e_["Value"]}
                    end,
                    Load = function(o9, jM)
                        if Toggles[o9] then
                            Toggles[o9]:SetValue(jM.value)
                        end
                    end
                },
                Slider = {
                    Save = function(o9, e_)
                        return {type = "Slider", idx = o9, value = tostring(e_.Value)}
                    end,
                    Load = function(o9, jM)
                        if Options[o9] then
                            Options[o9]:SetValue(tonumber(jM.value))
                        end
                    end
                },
                Dropdown = {
                    Save = function(o9, e_)
                        return {type = "Dropdown", idx = o9, value = e_["Value"], multi = e_["Multi"]}
                    end,
                    Load = function(o9, jM)
                        if ((479 < 1863) and Options[o9]) then
                            Options[o9]:SetValue(jM.value)
                        end
                    end
                },
                ColorPicker = {
                    Save = function(o9, e_)
                        return {
                            type = "ColorPicker",
                            idx = o9,
                            value = e_["Value"]:ToHex(),
                            transparency = e_["Transparency"]
                        }
                    end,
                    Load = function(o9, jM)
                        if Options[o9] then
                            Options[o9]:SetValueRGB(Color3.fromHex(jM.value), jM.transparency)
                        end
                    end
                },
                KeyPicker = {
                    Save = function(o9, e_)
                        return {type = "KeyPicker", idx = o9, mode = e_["Mode"], key = e_["Value"]}
                    end,
                    Load = function(o9, jM)
                        if Options[o9] then
                            Options[o9]:SetValue({jM["key"], jM["mode"]})
                        end
                    end
                },
                Input = {
                    Save = function(o9, e_)
                        return {type = "Input", idx = o9, text = e_["Value"]}
                    end,
                    Load = function(o9, jM)
                        if ((Options[o9] and (type(jM.text) == "string")) or (2428 >= 4038)) then
                            Options[o9]:SetValue(jM.text)
                        end
                    end
                }
            }
            o8.setIgnore = function(self, oa)
                for D, d_ in pairs(oa) do
                    self["ignore"][d_] = true
                end
            end
            o8.setFolder = function(self, ob)
                self["folder"] = ob
                self:buildTree()
            end
            o8.save = function(self, ec)
                if not ec then
                    return false, "no config selected"
                end
                local jV = self["folder"] .. "/settings/" .. ec .. ".json"
                local jM = {objects = {}}
                for o9, oc in pairs(Toggles) do
                    if (not self["ignore"][o9] or (2878 > 2897)) then
                        table.insert(jM.objects, self["parser"][oc["Type"]].Save(o9, oc))
                    end
                end
                for o9, od in pairs(Options) do
                    if (self["parser"][od["Type"]] and not self["ignore"][o9]) then
                        table.insert(jM.objects, self["parser"][od["Type"]].Save(o9, od))
                    end
                end
                local B, oe = pcall(mp.JSONEncode, mp, jM)
                if (not B or (2469 > 3676)) then
                    return false, "encode error"
                end
                writefile(jV, oe)
                return true
            end
            o8.load = function(self, ec)
                if not ec then
                    return false, "no config selected"
                end
                local mU = self["folder"] .. "/settings/" .. ec .. ".json"
                if not isfile(mU) then
                    return false, "invalid file"
                end
                local B, of = pcall(mp.JSONDecode, mp, readfile(mU))
                if not B then
                    return false, "decode error"
                end
                for D, od in pairs(of.objects) do
                    if self["parser"][od["type"]] then
                        task.spawn(
                            function()
                                self["parser"][od["type"]].Load(od.idx, od)
                            end
                        )
                    end
                end
                return true
            end
            o8.ignoreTheme = function(self)
                self:setIgnore(
                    {
                        "BackgroundColor",
                        "MainColor",
                        "AccentColor",
                        "OutlineColor",
                        "FontColor",
                        "ThemeManager_ThemeList",
                        "ThemeManager_CustomThemeList",
                        "ThemeManager_CustomThemeName"
                    }
                )
            end
            o8.buildTree = function(self)
                local og = {self["folder"], (self["folder"] .. "/themes"), (self["folder"] .. "/settings")}
                for w = 1, #og do
                    if ((233 < 487) and not isfolder(og[w])) then
                        makefolder(og[w])
                    end
                end
            end
            o8.refresh = function(self)
                local oa = listfiles(self["folder"] .. "/settings")
                local oh = {}
                for w = 1, #oa do
                    local mU = oa[w]
                    if (mU:sub(-5) ~= ".json") then
                    else
                        local en = mU:find(".json", 1, true)
                        local e1 = en
                        local dS = mU:sub(en, en)
                        while (dS ~= "/") and (dS ~= "\\") and (dS ~= "") do
                            en = en - 1
                            dS = mU:sub(en, en)
                        end
                        if ((dS == "/") or (dS == "\\")) then
                            table.insert(oh, mU:sub(en + 1, e1 - 1))
                        end
                    end
                end
                return oh
            end
            o8.setLibrary = function(self, mu)
                self["library"] = mu
            end
            o8.autoload = function(self)
                if isfile(self["folder"] .. "/settings/autoload.txt") then
                    local ec = readfile(self["folder"] .. "/settings/autoload.txt")
                    local B, oi = self:load(ec)
                    if not B then
                        return self["library"]:Notify("Failed to load autoload: " .. oi)
                    end
                    self["library"]:Notify(string.format("Auto loaded config %q", ec))
                end
            end
            o8.buildSection = function(self, oj)
                assert(self.library, "Must set library first")
                oj:AddInput("ConfigManager_Name", {Text = "Config name"})
                oj:AddDropdown("ConfigManager_List", {Text = "Config list", Values = self:refresh(), AllowNull = true})
                oj:AddDivider()
                oj:AddButton(
                    "Create config",
                    function()
                        local ec = Options["ConfigManager_Name"]["Value"]
                        if ((2473 >= 201) and (ec:gsub(" ", "") == "")) then
                            return self["library"]:Notify("Invalid config name", 2)
                        end
                        local B, oi = self:save(ec)
                        if ((4120 >= 133) and not B) then
                            return self["library"]:Notify("Failed to save: " .. oi)
                        end
                        self["library"]:Notify(string.format("Created config %q", ec))
                        Options["ConfigManager_List"]:SetValues(self:refresh())
                        Options["ConfigManager_List"]:SetValue(nil)
                    end
                ):AddButton(
                    "Load config",
                    function()
                        local ec = Options["ConfigManager_List"]["Value"]
                        local B, oi = self:load(ec)
                        if ((3080 >= 1986) and not B) then
                            return self["library"]:Notify("Failed to load: " .. oi)
                        end
                        self["library"]:Notify(string.format("Loaded config %q", ec))
                    end
                )
                oj:AddButton(
                    "Overwrite config",
                    function()
                        local ec = Options["ConfigManager_List"]["Value"]
                        local B, oi = self:save(ec)
                        if (not B or (1439 > 3538)) then
                            return self["library"]:Notify("Failed to overwrite: " .. oi)
                        end
                        self["library"]:Notify(string.format("Overwrote config %q", ec))
                    end
                )
                oj:AddButton(
                    "Refresh list",
                    function()
                        Options["ConfigManager_List"]:SetValues(self:refresh())
                        Options["ConfigManager_List"]:SetValue(nil)
                    end
                )
                oj:AddButton(
                    "Set as autoload",
                    function()
                        local ec = Options["ConfigManager_List"]["Value"]
                        writefile(self["folder"] .. "/settings/autoload.txt", ec)
                        o8["autoloadLabel"]:SetText("Current autoload: " .. ec)
                        self["library"]:Notify(string.format("Set %q to autoload", ec))
                    end
                )
                o8["autoloadLabel"] = oj:AddLabel("Current autoload: none", true)
                if (isfile(self["folder"] .. "/settings/autoload.txt") or (419 < 7)) then
                    local ec = readfile(self["folder"] .. "/settings/autoload.txt")
                    o8["autoloadLabel"]:SetText("Current autoload: " .. ec)
                end
                self:setIgnore({"ConfigManager_List", "ConfigManager_Name"})
            end
            o8:buildTree()
        end
        return o8
    end,
    HUD = function()
        return function(oj, nP, dL)

oj:AddToggle("HUD_Watermark", {Text = "Watermark", Default = false})

-- Variable para controlar el bucle
local UpdateWatermark = false

Toggles["HUD_Watermark"]:OnChanged(function()
    local state = Toggles["HUD_Watermark"].Value
    UpdateWatermark = state
    nP:SetWatermarkVisibility(state)
    
    if state then
        dL.spawn(function()
            while UpdateWatermark do
                -- Obtener FPS y Ping (MS)
                local fps = math.floor(1 / dL.wait())
                local ping = math.floor(game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValue())
                
                -- Texto simple sin etiquetas de color
                local text = string.format(
                    "intellect.club | %d fps | %d ms",
                    fps, 
                    ping
                )
                
                nP:SetWatermark(text)

                -- Centrar el Watermark en la pantalla
                if nP["WatermarkFrame"] then
                    nP["WatermarkFrame"]["Position"] = UDim2.new(0.5, -nP["WatermarkFrame"]["AbsoluteSize"]["X"] / 2, 0, 10)
                end
                
                task.wait(1)
            end
        end)
    end
end)
            oj:AddLabel("Menu Bind"):AddKeyPicker(
                "HUD_MenuBind",
                {Default = "RightControl", Text = "Menu Bind", Mode = "Toggle", SyncToggleState = false}
            )
            nP["MenuKeybind"] = Options["HUD_MenuBind"]
            Options["HUD_MenuBind"]:OnClick(
                function()
                    nP:Toggle()
                end
            )
            nP:OnUnload(
                function()
                    Toggles["HUD_Keybinds"]:SetValue(false)
                    Toggles["HUD_Watermark"]:SetValue(false)
                end
            )
        end
    end,
    ServerUtils = function()
        local ok = {}
        do
            ok.buildSection = function(self, oj, mu, dL)
                oj:AddButton(
                    {
                        Text = "Copy jobId",
                        Func = function()
                            setclipboard(game.JobId)
                            mu:Notify("Success", 2)
                        end
                    }
                )
                oj:AddButton(
                    {
                        Text = "Copy gameID",
                        Func = function()
                            setclipboard(tostring(game.GameId))
                            mu:Notify("Success", 2)
                        end
                    }
                )
                oj:AddButton(
                    {
                        Text = "Copy join script",
                        Func = function()
                            setclipboard(
                                'game:GetService("TeleportService"):TeleportToPlaceInstance(' ..
                                    game["PlaceId"] .. ',"' .. game["JobId"] .. '",game.Players.LocalPlayer)'
                            )
                            mu:Notify("Success", 2)
                        end
                    }
                )
                oj:AddButton(
                    {
                        Text = "Rejoin",
                        Func = function()
                            mu:Notify("Success", 2)
                            dL["teleport"]:TeleportToPlaceInstance(game.PlaceId, game.JobId, dL.lp)
                        end
                    }
                )
                oj:AddDivider()
                oj:AddButton(
                    {
                        Text = "Join new server",
                        Func = function()
                            local hT, kw =
                                Options["ServerUtils_MinPlayers"]["Value"],
                                Options["ServerUtils_MaxPlayers"]["Value"]
                            local B, jM =
                                pcall(
                                function()
                                    return dL["http"]:JSONDecode(
                                        game:HttpGetAsync(
                                            "https://games.roblox.com/v1/games/" ..
                                                game["PlaceId"] .. "/servers/Public?sortOrder=Asc&limit=100"
                                        )
                                    )
                                end
                            )
                            if not B then
                                return mu:Notify("Rejected", 2)
                            end
                            local ol = {}
                            for D, om in pairs(jM.data) do
                                if ((om["playing"] >= hT) and (om["playing"] <= kw)) then
                                    dL.insert(ol, om)
                                end
                            end
                            if ((2820 == 2820) and (#ol > 0)) then
                                mu:Notify("Success", 2)
                                dL["teleport"]:TeleportToPlaceInstance(game.PlaceId, ol[dL.random(1, #ol)].id, dL.lp)
                            else
                                mu:Notify("Rejected", 2)
                            end
                        end
                    }
                )
                oj:AddSlider(
                    "ServerUtils_MinPlayers",
                    {Text = "Min players", Default = 1, Min = 0, Max = 40, Rounding = 0}
                )
                oj:AddSlider(
                    "ServerUtils_MaxPlayers",
                    {Text = "Max players", Default = 15, Min = 0, Max = 40, Rounding = 0}
                )
            end
        end
        return ok
    end,
    ThemeManager = function()
        local mp = cloneref(game:GetService("HttpService"))
        local o8 = {}
        do
            o8["folder"] = "intellectSettings"
            o8["library"] = nil
            o8["themes"] = {
                Default = {
                    1,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"1c1c1c","AccentColor":"0055ff","BackgroundColor":"141414","OutlineColor":"323232"}'
                    )
                },
                BBot = {
                    2,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"1e1e1e","AccentColor":"7e48a3","BackgroundColor":"232323","OutlineColor":"141414"}'
                    )
                },
                Fatality = {
                    3,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"1e1842","AccentColor":"c50754","BackgroundColor":"191335","OutlineColor":"3c355d"}'
                    )
                },
                Jester = {
                    4,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"242424","AccentColor":"db4467","BackgroundColor":"1c1c1c","OutlineColor":"373737"}'
                    )
                },
                Mint = {
                    5,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"242424","AccentColor":"3db488","BackgroundColor":"1c1c1c","OutlineColor":"373737"}'
                    )
                },
                ["Tokyo Night"] = {
                    6,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"191925","AccentColor":"6759b3","BackgroundColor":"16161f","OutlineColor":"323232"}'
                    )
                },
                Ubuntu = {
                    7,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"3e3e3e","AccentColor":"e2581e","BackgroundColor":"323232","OutlineColor":"191919"}'
                    )
                },
                Quartz = {
                    8,
                    mp:JSONDecode(
                        '{"FontColor":"ffffff","MainColor":"232330","AccentColor":"426e87","BackgroundColor":"1d1b26","OutlineColor":"27232f"}'
                    )
                }
            }
            o8.apply = function(self, on)
                local oo = self:getCustom(on)
                local jM = oo or self["themes"][on]
                if (not jM or (4362 <= 3527)) then
                    return
                end
                local op = jM[2]
                for o9, j0 in pairs(oo or op) do
                    self["library"][o9] = Color3.fromHex(j0)
                    if Options[o9] then
                        Options[o9]:SetValueRGB(Color3.fromHex(j0))
                    end
                end
                self:update()
            end
            o8.update = function(self)
                local nS = {"FontColor", "MainColor", "AccentColor", "BackgroundColor", "OutlineColor"}
                for w, oq in pairs(nS) do
                    if (Options and Options[oq]) then
                        self["library"][oq] = Options[oq]["Value"]
                    end
                end
                self["library"]["AccentColorDark"] = self["library"]:GetDarkerColor(self["library"].AccentColor)
                self["library"]:UpdateColorsUsingRegistry()
            end
            o8.loadDefault = function(self)
                local on = "Default"
                local ot =
                    isfile(self["folder"] .. "/themes/default.txt") and
                    readfile(self["folder"] .. "/themes/default.txt")
                local ou = true
                if ot then
                    if self["themes"][ot] then
                        on = ot
                    elseif self:getCustom(ot) then
                        on = ot
                        ou = false
                    end
                elseif self["themes"][self["defaultTheme"]] then
                    on = self["defaultTheme"]
                end
                if ((2613 <= 2680) and ou) then
                    Options["ThemeManager_ThemeList"]:SetValue(on)
                else
                    self:apply(on)
                end
            end
            o8.saveDefault = function(self, on)
                writefile(self["folder"] .. "/themes/default.txt", on)
            end
            o8.create = function(self, oj)
                oj:AddLabel("Background color"):AddColorPicker(
                    "BackgroundColor",
                    {Default = self["library"]["BackgroundColor"]}
                )
                oj:AddLabel("Main color"):AddColorPicker("MainColor", {Default = self["library"]["MainColor"]})
                oj:AddLabel("Accent color"):AddColorPicker("AccentColor", {Default = self["library"]["AccentColor"]})
                oj:AddLabel("Outline color"):AddColorPicker("OutlineColor", {Default = self["library"]["OutlineColor"]})
                oj:AddLabel("Font color"):AddColorPicker("FontColor", {Default = self["library"]["FontColor"]})
                local ov = {}
                for ec, on in pairs(self.themes) do
                    table.insert(ov, ec)
                end
                table.sort(
                    ov,
                    function(jj, aZ)
                        return self["themes"][jj][1] < self["themes"][aZ][1]
                    end
                )
                oj:AddDivider()
                oj:AddDropdown("ThemeManager_ThemeList", {Text = "Theme list", Values = ov, Default = 1})
                oj:AddButton(
                    "Set as default",
                    function()
                        self:saveDefault(Options["ThemeManager_ThemeList"].Value)
                        self["library"]:Notify(
                            string.format("Set default theme to %q", Options["ThemeManager_ThemeList"].Value)
                        )
                    end
                )
                Options["ThemeManager_ThemeList"]:OnChanged(
                    function()
                        self:apply(Options["ThemeManager_ThemeList"].Value)
                    end
                )
                oj:AddDivider()
                oj:AddInput("ThemeManager_CustomThemeName", {Text = "Custom theme name"})
                oj:AddDropdown(
                    "ThemeManager_CustomThemeList",
                    {Text = "Custom themes", Values = self:reloadCustom(), AllowNull = true, Default = 1}
                )
                oj:AddDivider()
                oj:AddButton(
                    "Save theme",
                    function()
                        self:saveCustom(Options["ThemeManager_CustomThemeName"].Value)
                        Options["ThemeManager_CustomThemeList"]:SetValues(self:reloadCustom())
                        Options["ThemeManager_CustomThemeList"]:SetValue(nil)
                    end
                ):AddButton(
                    "Load theme",
                    function()
                        self:apply(Options["ThemeManager_CustomThemeList"].Value)
                    end
                )
                oj:AddButton(
                    "Refresh list",
                    function()
                        Options["ThemeManager_CustomThemeList"]:SetValues(self:reloadCustom())
                        Options["ThemeManager_CustomThemeList"]:SetValue(nil)
                    end
                )
                oj:AddButton(
                    "Set as default",
                    function()
                        if
                            (((Options["ThemeManager_CustomThemeList"]["Value"] ~= nil) and
                                (Options["ThemeManager_CustomThemeList"]["Value"] ~= "")) or
                                (1482 >= 4288))
                         then
                            self:saveDefault(Options["ThemeManager_CustomThemeList"].Value)
                            self["library"]:Notify(
                                string.format("Set default theme to %q", Options["ThemeManager_CustomThemeList"].Value)
                            )
                        end
                    end
                )
                self:loadDefault()
                local function ow()
                    self:update()
                end
                Options["BackgroundColor"]:OnChanged(ow)
                Options["MainColor"]:OnChanged(ow)
                Options["AccentColor"]:OnChanged(ow)
                Options["OutlineColor"]:OnChanged(ow)
                Options["FontColor"]:OnChanged(ow)
            end
            o8.getCustom = function(self, mU)
                local jV = self["folder"] .. "/themes/" .. mU
                if (not isfile(jV) or (2462 > 4426)) then
                    return nil
                end
                local jM = readfile(jV)
                local B, of = pcall(mp.JSONDecode, mp, jM)
                if ((4774 == 4774) and not B) then
                    return nil
                end
                return of
            end
            o8.saveCustom = function(self, mU)
                if (mU:gsub(" ", "") ~= "") then
                else
                    return self["library"]:Notify("Invalid theme name", 3)
                end
                local on = {}
                local ox = {"FontColor", "MainColor", "AccentColor", "BackgroundColor", "OutlineColor"}
                for D, oq in pairs(ox) do
                    on[oq] = Options[oq]["Value"]:ToHex()
                end
                writefile(self["folder"] .. "/themes/" .. mU .. ".json", mp:JSONEncode(on))
            end
            o8.reloadCustom = function(self)
                local oa = listfiles(self["folder"] .. "/themes")
                local oh = {}
                for w = 1, #oa do
                    local mU = oa[w]
                    if ((566 <= 960) and (mU:sub(-5) == ".json")) then
                        local en = mU:find(".json", 1, true)
                        local dS = mU:sub(en, en)
                        while (dS ~= "/") and (dS ~= "\\") and (dS ~= "") do
                            en = en - 1
                            dS = mU:sub(en, en)
                        end
                        if ((dS == "/") or (dS == "\\") or (2910 <= 1930)) then
                            table.insert(oh, mU:sub(en + 1))
                        end
                    end
                end
                return oh
            end
            o8.setLibrary = function(self, mu)
                self["library"] = mu
            end
            o8.buildTree = function(self)
                local hm = self["folder"]:split("/")
                local og = {}
                for o9 = 1, #hm do
                    og[#og + 1] = table.concat(hm, "/", 1, o9)
                end
                table.insert(og, self["folder"] .. "/themes")
                table.insert(og, self["folder"] .. "/settings")
                for w = 1, #og do
                    if not isfolder(og[w]) then
                        makefolder(og[w])
                    end
                end
            end
            o8.setFolder = function(self, ob)
                self["folder"] = ob
                self:buildTree()
            end
            o8.createGroupbox = function(self, oy)
                assert(self.library, "Must set library first")
                return oy:AddLeftGroupbox("Themes")
            end
            o8.applyToTab = function(self, oy)
                assert(self.library, "Must set library first")
                local oj = self:createGroupbox(oy)
                self:create(oj)
            end
            o8.applyToGroupbox = function(self, oj)
                assert(self.library, "Must set library first")
                self:create(oj)
            end
            o8:buildTree()
        end
        return o8
    end
}
local getgenv = getgenv or function()
        return _G
    end
getgenv()["config"] = getgenv()["config"] or {}
getgenv()["flags"] = getgenv()["flags"] or {}
local oz = {}
do
    for ec, oA in pairs(f) do
        local B, aW = pcall(oA)
        if B then
            oz[ec] = aW
        else

        end
    end
end
local eZ = oz["Api_LPH_Init"]()
local dL = oz["Api_Services"]()
dL["hooks"] = oz["Api_Hooks"](dL)
dL["desync"] = oz["Api_Desync"](dL)
dL["targeting"] = oz["Api_Targeting"](dL)
dL["targeting"]:init()
local nP = oz["UILibrary"]
if not nP then

    return
end
local oB = {}
do
    oB.getClosestPlayerToCursor = function(self, oC)
        local eH = nil
        local oD = oC or dL["huge"]
        for D, eV in pairs(dL["players"]:GetPlayers()) do
            if ((eV ~= dL["lp"]) and eV["Character"] and eV["Character"]:FindFirstChild("HumanoidRootPart")) then
                local ev = eV["Character"]["HumanoidRootPart"]
                local ew, eo = dL["camera"]:WorldToScreenPoint(ev.Position)
                if eo then
                    local ex = dL["userinput"]:GetMouseLocation()
                    local fn = (dL.v2(ew.X, ew.Y) - ex)["Magnitude"]
                    if ((fn < oD) or (19 > 452)) then
                        oD = fn
                        eH = eV
                    end
                end
            end
        end
        return eH
    end
end
local kF = {connections = {}}
do
    kF.cleanup = function(self)
        for D, bK in pairs(self.connections) do
            if bK then
                bK:Disconnect()
            end
        end
        self["connections"] = {}
    end
end
local oE = oz["ThemeManager"]
local oF = oz["ConfigManager"]
local oG = oz["ServerUtils"]
do
local oH = nP:CreateWindow({
    Title = "home",
    Center = true,
    AutoShow = true,
    TabPadding = 0,
    MenuFadeTime = 0.15,
})


local legitbot = oH:AddTab(" legitbot ") 
local Players = game:GetService("Players") 
local RunService = game:GetService("RunService") 
local UserInputService = game:GetService("UserInputService") 
local Camera = workspace.CurrentCamera 
local LocalPlayer = Players.LocalPlayer 
local Mouse = LocalPlayer:GetMouse() 

getgenv().CamlockEnabled = false 
getgenv().CamlockKeyActive = false 
getgenv().CamlockHitPart = "Head" 
getgenv().CamlockSmoothness = 0.12 
getgenv().CamlockPrediction = 0.09 

-- TRIGGERBOT SETTINGS 
getgenv().TriggerEnabled = false 
getgenv().TriggerKeyActive = false 
getgenv().TriggerDelay = 0.1 

-- ==================================== 
-- UI 
-- ==================================== 

-- CAMLOCK SECTION 
local CamSection = legitbot:AddLeftGroupbox("Aim Assist") 
CamSection:AddToggle("CamlockToggle", { 
    Text = "Enable", 
    Default = false, 
    Callback = function(state) 
        getgenv().CamlockEnabled = state 
        if not state then getgenv().CamlockKeyActive = false end 
    end 
}):AddKeyPicker("CamlockKeybind", { 
    Default = "Q", 
    Mode = "Toggle", 
    SyncToggleState = false, 
    Text = "Keybind", 
    Callback = function(state) 
        if getgenv().CamlockEnabled then getgenv().CamlockKeyActive = state end 
    end 
}) 

CamSection:AddDropdown("CamlockHitbox", { 
    Text = "Hitbox", 
    Values = { "Head","UpperTorso","LowerTorso","HumanoidRootPart", "LeftUpperArm","LeftLowerArm","RightUpperArm","RightLowerArm", "LeftUpperLeg","LeftLowerLeg","RightUpperLeg","RightLowerLeg" }, 
    Default = 1, 
    Callback = function(value) getgenv().CamlockHitPart = value end 
}) 

CamSection:AddSlider("CamlockSmoothnessSlider", { 
    Text = "Smoothing", 
    Default = getgenv().CamlockSmoothness, 
    Min = 0.01, 
    Max = 1, 
    Rounding = 3, 
    Callback = function(value) getgenv().CamlockSmoothness = value end 
}) 

CamSection:AddSlider("CamlockPredictionSlider", { 
    Text = "Prediction", 
    Default = getgenv().CamlockPrediction, 
    Min = 0, 
    Max = 1, 
    Rounding = 3, 
    Callback = function(value) getgenv().CamlockPrediction = value end 
}) 

-- TRIGGERBOT SECTION 
local TriggerSection = legitbot:AddLeftGroupbox("Triggerbot") 
TriggerSection:AddToggle("TriggerToggle", { 
    Text = "Enable", 
    Default = false, 
    Callback = function(state) 
        getgenv().TriggerEnabled = state 
        if not state then getgenv().TriggerKeyActive = false end 
    end 
}):AddKeyPicker("TriggerKeybind", { 
    Default = "Z", 
    Mode = "Toggle", 
    SyncToggleState = false, 
    Text = "Keybind", 
    Callback = function(state) 
        if getgenv().TriggerEnabled then getgenv().TriggerKeyActive = state end 
    end 
}) 

TriggerSection:AddSlider("TriggerDelaySlider", { 
    Text = "Delay", 
    Default = getgenv().TriggerDelay, 
    Min = 0.01, 
    Max = 1, 
    Rounding = 2, 
    Callback = function(value) getgenv().TriggerDelay = value end 
}) 

-- ==================================== 
-- UTILITY FUNCTIONS 
-- ==================================== 

local function GetClosestToCenter() 
    local Closest, Distance = nil, math.huge 
    for _, Player in pairs(Players:GetPlayers()) do 
        if Player ~= LocalPlayer and Player.Character and Player.Character:FindFirstChild(getgenv().CamlockHitPart) then 
            local Pos, OnScreen = Camera:WorldToViewportPoint(Player.Character[getgenv().CamlockHitPart].Position) 
            if OnScreen then 
                local Dist = (Vector2.new(Pos.X, Pos.Y) - UserInputService:GetMouseLocation()).Magnitude 
                if Dist < Distance then 
                    Closest = Player 
                    Distance = Dist 
                end 
            end 
        end 
    end 
    return Closest 
end 

local function GetPlayerFromPart(part) 
    for _, plr in ipairs(Players:GetPlayers()) do 
        if plr ~= LocalPlayer and plr.Character and part:IsDescendantOf(plr.Character) then 
            return plr 
        end 
    end 
end 

-- ==================================== 
-- CAMLOCK LOOP 
-- ==================================== 

local CamTarget = nil 
RunService.RenderStepped:Connect(function() 
    if not getgenv().CamlockEnabled then 
        CamTarget = nil 
        return 
    end 
    if getgenv().CamlockKeyActive then 
        if not CamTarget or not CamTarget.Character or not CamTarget.Character:FindFirstChild(getgenv().CamlockHitPart) then 
            CamTarget = GetClosestToCenter() 
        end 
        if CamTarget and CamTarget.Character then 
            local Part = CamTarget.Character:FindFirstChild(getgenv().CamlockHitPart) 
            if Part then 
                local Predicted = Part.Position + (Part.Velocity * getgenv().CamlockPrediction) 
                Camera.CFrame = Camera.CFrame:Lerp(CFrame.new(Camera.CFrame.Position, Predicted), getgenv().CamlockSmoothness) 
            end 
        end 
    else 
        CamTarget = nil 
    end 
end) 

-- ==================================== 
-- TRIGGERBOT LOOP 
-- ==================================== 

RunService.Heartbeat:Connect(function() 
    if not getgenv().TriggerEnabled or not getgenv().TriggerKeyActive then return end 
    local part = Mouse.Target 
    if part then 
        local plr = GetPlayerFromPart(part) 
        if plr and LocalPlayer.Character then 
            local Tool = LocalPlayer.Character:FindFirstChildWhichIsA("Tool") 
            if Tool then 
                task.wait(getgenv().TriggerDelay) 
                Tool:Activate() 
            end 
        end 
    end 
end) 

local Players = game:GetService("Players") 
local RunService = game:GetService("RunService") 
local UserInputService = game:GetService("UserInputService") 
local Camera = workspace.CurrentCamera 
local LocalPlayer = Players.LocalPlayer 
local Mouse = LocalPlayer:GetMouse() 
local DrawingNew = Drawing.new 

-- [[ SILENT AIM SETTINGS ]] 
getgenv().SilentAimEnabled = false 
getgenv().SilentAimKeyActive = false 
getgenv().SilentAimHitPart = "Head" 
getgenv().SilentAimPrediction = 0.1 
getgenv().SilentAimFOVVisible = true 
getgenv().SilentAimFOVRadius = 150 
getgenv().SilentAimFOVTransparency = 1 
getgenv().SilentAimFOVThickness = 1 
getgenv().SilentAimFOVColor = Color3.fromRGB(255, 255, 255) 

-- ==================================== 
-- UI 
-- ==================================== 

local SilentSection = legitbot:AddLeftGroupbox("Silent Aim") 
SilentSection:AddToggle("SilentAimToggle", { 
    Text = "Enable", 
    Default = false, 
    Callback = function(state) 
        getgenv().SilentAimEnabled = state 
        if not state then getgenv().SilentAimKeyActive = false end 
    end 
}):AddKeyPicker("SilentAimKeybind", { 
    Default = "K", 
    Mode = "Toggle", 
    SyncToggleState = false, 
    Text = "Keybind", 
    Callback = function(state) 
        if getgenv().SilentAimEnabled then getgenv().SilentAimKeyActive = state end 
    end 
}) 

SilentSection:AddDropdown("SilentAimHitbox", { 
    Text = "Hitbox", 
    Values = { "Head","UpperTorso","LowerTorso","HumanoidRootPart", "LeftUpperArm","LeftLowerArm","RightUpperArm","RightLowerArm", "LeftUpperLeg","LeftLowerLeg","RightUpperLeg","RightLowerLeg", "LeftHand","RightHand","LeftFoot","RightFoot" }, 
    Default = 1, 
    Callback = function(value) getgenv().SilentAimHitPart = value end 
}) 

SilentSection:AddSlider("SilentAimPredictionSlider", { 
    Text = "Prediction", 
    Default = getgenv().SilentAimPrediction, 
    Min = 0, 
    Max = 1, 
    Rounding = 3, 
    Callback = function(value) getgenv().SilentAimPrediction = value end 
}) 

SilentSection:AddToggle("FOVVisibleToggle", { 
    Text = "Show FOV", 
    Default = getgenv().SilentAimFOVVisible, 
    Callback = function(state) getgenv().SilentAimFOVVisible = state end 
}) 

SilentSection:AddSlider("FOVRadiusSlider", { 
    Text = "Field of View", 
    Default = getgenv().SilentAimFOVRadius, 
    Min = 50, 
    Max = 500, 
    Rounding = 0, 
    Callback = function(value) getgenv().SilentAimFOVRadius = value end 
}) 

-- ==================================== 
-- DRAWING FOV 
-- ==================================== 

local FOVCircle = DrawingNew("Circle") 
FOVCircle.Filled = false 
FOVCircle.Thickness = getgenv().SilentAimFOVThickness 
FOVCircle.Transparency = getgenv().SilentAimFOVTransparency 
FOVCircle.Color = getgenv().SilentAimFOVColor 

RunService.RenderStepped:Connect(function() 
    if FOVCircle then 
        FOVCircle.Visible = getgenv().SilentAimFOVVisible and getgenv().SilentAimEnabled and getgenv().SilentAimKeyActive 
        FOVCircle.Radius = getgenv().SilentAimFOVRadius 
        FOVCircle.Position = UserInputService:GetMouseLocation() 
    end 
end) 

-- ==================================== 
-- UTILITY FUNCTION 
-- ==================================== 

local function GetClosestPlayer() 
    local ClosestDistance, ClosestPart = nil, nil 
    local MousePos = UserInputService:GetMouseLocation() 
    for _, Player in pairs(Players:GetPlayers()) do 
        if Player ~= LocalPlayer and Player.Character then 
            local Character = Player.Character 
            local Part = Character:FindFirstChild(getgenv().SilentAimHitPart) 
            local Humanoid = Character:FindFirstChild("Humanoid") 
            if Part and Humanoid and Humanoid.Health > 0 then 
                local ScreenPos, OnScreen = Camera:WorldToScreenPoint(Part.Position) 
                if OnScreen then 
                    local Dist = (Vector2.new(ScreenPos.X, ScreenPos.Y) - MousePos).Magnitude 
                    if Dist <= getgenv().SilentAimFOVRadius and (not ClosestDistance or Dist < ClosestDistance) then 
                        ClosestDistance, ClosestPart = Dist, Part 
                    end 
                end 
            end 
        end 
    end 
    return ClosestPart 
end 

-- ==================================== 
-- HOOK MOUSE HIT 
-- ==================================== 

local grm = getrawmetatable(game) 
local oldIndex = grm.__index 
setreadonly(grm, false) 
grm.__index = newcclosure(function(self, Index) 
    if not checkcaller() and self == Mouse and getgenv().SilentAimEnabled and getgenv().SilentAimKeyActive then 
        if Index == "Hit" or Index == "Target" then 
            local Target = GetClosestPlayer() 
            if Target then 
                return CFrame.new(Target.Position + (Target.Velocity * getgenv().SilentAimPrediction)) 
            end 
        end 
    end 
    return oldIndex(self, Index) 
end) 
setreadonly(grm, true)



    local oI = {Ragebot = oH:AddTab(" ragebot "),  Visuals = oH:AddTab(" visuals "),  Settings = oH:AddTab(" settings ")}


local Test = oH:AddTab(" misc ")



local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local LocalPlayer = Players.LocalPlayer


getgenv().walkSpeedEnabled = false
getgenv().walkSpeedKeybindActive = false
getgenv().walkSpeed = 16

getgenv().FlightEnabled = false
getgenv().Flying = false
getgenv().FlySpeed = 50

getgenv().SpinbotEnabled = false
getgenv().SpinSpeed = 10
getgenv().SpinConnection = nil

getgenv().AnimationEnabled = false
getgenv().AnimationSpeed = 1
getgenv().AnimationJitter = 0
getgenv().AnimationID = ""

local animationTrack
local isPlaying = false

-- BACKEND FUNCTIONS
function stopAnimation()
    if animationTrack then
        pcall(function() animationTrack:Stop() end)
        animationTrack = nil
        isPlaying = false
    end
end

function loadAnimationOnCharacter(char)
    if not char or getgenv().AnimationID == "" then return end
    local humanoid = char:FindFirstChildOfClass("Humanoid")
    if not humanoid then return end
    stopAnimation()
    local anim = Instance.new("Animation")
    anim.AnimationId = "rbxassetid://"..getgenv().AnimationID
    local animator = humanoid:FindFirstChildOfClass("Animator")
    if not animator then
        animator = Instance.new("Animator", humanoid)
    end
    local ok, track = pcall(function() return animator:LoadAnimation(anim) end)
    if ok then
        animationTrack = track
        animationTrack.Looped = true
        animationTrack.Priority = Enum.AnimationPriority.Action
        if getgenv().AnimationEnabled then
            animationTrack:Play()
            animationTrack:AdjustSpeed(getgenv().AnimationSpeed)
            isPlaying = true
        end
    end
end

function startFly()
    if getgenv().Flying then return end
    getgenv().Flying = true
    local char = LocalPlayer.Character
    if not char then return end
    local humanoid = char:FindFirstChild("Humanoid")
    if humanoid then humanoid.PlatformStand = true end
    local core = Instance.new("Part")
    core.Name = "FlightCore"
    core.Size = Vector3.new(0.05,0.05,0.05)
    core.Transparency = 1
    core.CanCollide = false
    core.Anchored = false
    core.Parent = workspace
    local weld = Instance.new("Weld", core)
    weld.Part0 = core
    weld.Part1 = LocalPlayer.Character.HumanoidRootPart
    weld.C0 = CFrame.new()
    local bv = Instance.new("BodyVelocity", core)
    bv.MaxForce = Vector3.new(9e9,9e9,9e9)
    local bg = Instance.new("BodyGyro", core)
    bg.MaxTorque = Vector3.new(9e9,9e9,9e9)
    bg.P = 9e4
    local conn
    conn = RunService.RenderStepped:Connect(function()
        if not getgenv().Flying then conn:Disconnect() return end
        local cam = workspace.CurrentCamera
        local direction = Vector3.zero
        if UserInputService:IsKeyDown(Enum.KeyCode.W) then direction += cam.CFrame.LookVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.S) then direction -= cam.CFrame.LookVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.A) then direction -= cam.CFrame.RightVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.D) then direction += cam.CFrame.RightVector end
        if UserInputService:IsKeyDown(Enum.KeyCode.Space) then direction += Vector3.new(0,1,0) end
        if UserInputService:IsKeyDown(Enum.KeyCode.LeftControl) then direction -= Vector3.new(0,1,0) end
        bv.Velocity = direction * getgenv().FlySpeed
        bg.CFrame = cam.CFrame
    end)
end

function stopFly()
    getgenv().Flying = false
    local char = LocalPlayer.Character
    if char then
        local humanoid = char:FindFirstChild("Humanoid")
        if humanoid then humanoid.PlatformStand = false end
    end
    if workspace:FindFirstChild("FlightCore") then workspace.FlightCore:Destroy() end
end

function toggleSpinbot(state)
    if state then
        if getgenv().SpinConnection then return end
        getgenv().SpinConnection = RunService.RenderStepped:Connect(function()
            local char = LocalPlayer.Character
            local hrp = char and char:FindFirstChild("HumanoidRootPart")
            local humanoid = char and char:FindFirstChild("Humanoid")
            if char and hrp and humanoid and not getgenv().Flying then
                humanoid.AutoRotate = false
                hrp.CFrame *= CFrame.Angles(0, math.rad(getgenv().SpinSpeed), 0)
            end
        end)
    else
        if getgenv().SpinConnection then
            getgenv().SpinConnection:Disconnect()
            getgenv().SpinConnection = nil
        end
        local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Humanoid")
        if humanoid then humanoid.AutoRotate = true end
    end
end

-- WalkSpeed updater
RunService.RenderStepped:Connect(function()
    local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
    if humanoid then
        humanoid.WalkSpeed = (getgenv().walkSpeedEnabled and getgenv().walkSpeedKeybindActive) and getgenv().walkSpeed or 16
    end
end)

-- Jitter loop
task.spawn(function()
    while task.wait(0.05) do
        if animationTrack and getgenv().AnimationJitter > 0 and isPlaying then
            local ok, cur = pcall(function() return animationTrack.TimePosition end)
            if ok and cur then
                animationTrack.TimePosition = math.max(0, cur + ((math.random()-0.5)*getgenv().AnimationJitter))
            end
        end
    end
end)

-----------------------------------------------------------
-- UI
-----------------------------------------------------------

-- WALK SPEED
local WalkBox = Test:AddLeftGroupbox("WalkSpeed")
local wsSlider = WalkBox:AddSlider("WalkSpeedSlider", {Text="Speed",Default=16,Min=16,Max=500,Rounding=0,Callback=function(v) getgenv().walkSpeed=v end})
wsSlider.Visible=false
WalkBox:AddToggle("WalkSpeedToggle",{Text="Enable",Default=false,Callback=function(state)
    getgenv().walkSpeedEnabled=state
    wsSlider.Visible=state
    if not state then getgenv().walkSpeedKeybindActive=false end
end}):AddKeyPicker("WalkSpeedKeybind",{Default="T",Text="Keybind",Mode="Toggle",Callback=function(state)
    if UserInputService:GetFocusedTextBox() then return end
    if getgenv().walkSpeedEnabled then getgenv().walkSpeedKeybindActive=state end
end})

-- FLIGHT
local FlyBox = Test:AddLeftGroupbox("Flight")
FlyBox:AddToggle("FlightToggle",{Text="Enable",Default=false,Callback=function(state)
    getgenv().FlightEnabled=state
    if not state then stopFly() end
end}):AddKeyPicker("FlightKeybind",{Default="X",Text="Keybind",Mode="Toggle",Callback=function(state)
    if UserInputService:GetFocusedTextBox() then return end
    getgenv().FlightEnabled=state
    if state then startFly() else stopFly() end
end})
FlyBox:AddSlider("FlySpeedSlider",{Text="Speed",Default=50,Min=10,Max=5000,Rounding=0,Callback=function(v) getgenv().FlySpeed=v end})

-- SPINBOT
local SpinBox = Test:AddRightGroupbox("Spinbot")
SpinBox:AddToggle("SpinbotToggle",{Text="Enable",Default=false,Callback=function(state)
    getgenv().SpinbotEnabled=state
    toggleSpinbot(state)
end}):AddKeyPicker("SpinbotKeybind",{Default="N",Text="Keybind",Mode="Toggle",Callback=function()
    if UserInputService:GetFocusedTextBox() then return end
    getgenv().SpinbotEnabled = not getgenv().SpinbotEnabled
    toggleSpinbot(getgenv().SpinbotEnabled)
end})
SpinBox:AddSlider("SpinSpeedSlider",{Text="Speed",Default=10,Min=1,Max=50,Rounding=1,Callback=function(v) getgenv().SpinSpeed=v end})

-- ANIMATION PLAYER
local AnimBox = Test:AddRightGroupbox("Animation Player")
local AnimNames = {"Custom","Floss","Yungblud","Hype","Sleepy","Laugh","Sad","Kicking Legs"}
local AnimationsMap = {["Floss"]="5917459365",["Yungblud"]="15609995579",["Hype"]="3695333486",["Sleepy"]="4686925579",["Laugh"]="3337966527",["Sad"]="4841407203",["Kicking Legs"]="120370790028350",["Custom"]=""}

AnimBox:AddToggle("AnimationToggle",{Text="Enable",Default=false,Callback=function(state)
    getgenv().AnimationEnabled=state
    if not animationTrack then loadAnimationOnCharacter(LocalPlayer.Character) end
    if animationTrack then
        if state then animationTrack:Play(); animationTrack:AdjustSpeed(getgenv().AnimationSpeed); isPlaying=true
        else animationTrack:Stop(); isPlaying=false end
    end
end}):AddKeyPicker("AnimationToggleKey",{Default="V",Text="Keybind",Mode="Toggle",Callback=function()
    if UserInputService:GetFocusedTextBox() then return end
    getgenv().AnimationEnabled = not getgenv().AnimationEnabled
    if not animationTrack then loadAnimationOnCharacter(LocalPlayer.Character) end
    if animationTrack then
        if getgenv().AnimationEnabled then animationTrack:Play(); animationTrack:AdjustSpeed(getgenv().AnimationSpeed); isPlaying=true
        else animationTrack:Stop(); isPlaying=false end
    end
end})

AnimBox:AddDropdown("AnimationSelector",{Text="Select Animation",Values=AnimNames,Default=1,Callback=function(name)
    local id=AnimationsMap[name]
    if name=="Custom" then stopAnimation() return end
    getgenv().AnimationID=id
    stopAnimation()
    loadAnimationOnCharacter(LocalPlayer.Character)
end})

AnimBox:AddInput("AnimationIDInput",{Text="Custom ID",Placeholder="Enter ID",Callback=function(v)
    local n=v:gsub("%s+","")
    if tonumber(n) then getgenv().AnimationID=n; stopAnimation(); loadAnimationOnCharacter(LocalPlayer.Character) end
end})

AnimBox:AddSlider("AnimationSpeedSlider",{Text="Speed",Default=1,Min=0.1,Max=30,Rounding=2,Callback=function(v)
    getgenv().AnimationSpeed=v
    if animationTrack and isPlaying then animationTrack:AdjustSpeed(v) end
end})

AnimBox:AddSlider("JitterSlider",{Text="Jitter",Default=0,Min=0,Max=30,Rounding=0,Callback=function(v) getgenv().AnimationJitter=v end})





LeftGroupBox = Test:AddLeftGroupbox('Unlock Camera Distance')
local Players = game:GetService("Players")
local player = Players.LocalPlayer

-- Guardar el zoom original
local originalZoom = player.CameraMaxZoomDistance

LeftGroupBox:AddToggle('MyToggle', {
    Text = 'Enable',
    Default = false,

    Callback = function(Value)
        if Value then
            -- Activar zoom infinito
            player.CameraMaxZoomDistance = math.huge
        else
            -- Restaurar zoom original
            player.CameraMaxZoomDistance = originalZoom
        end
    end
})

LeftGroupBox = Test:AddLeftGroupbox('Anti Stomp')

local RunService = game:GetService("RunService")
local player = game.Players.LocalPlayer
local debris = game:GetService("Debris")  -- For cleanup

-- Assuming LeftGroupBox and other UI elements are set up previously
local antiStompEnabled = false  -- Default value for anti-stomp toggle

-- Cache Enum values that are used frequently
local HumanoidStateType = Enum.HumanoidStateType
local KOD = "K.O"
local GRABBING_CONSTRAINT = "GRABBING_CONSTRAINT"

-- Add the Anti Stomp toggle
LeftGroupBox:AddToggle('MyToggle', {
    Text = 'Enable',
    Default = false, -- Default value (true / false)
    
    Callback = function(Value)
        antiStompEnabled = Value  -- Update the toggle value
    end
})

-- RunService heartbeat to monitor character state
RunService.Heartbeat:Connect(function()
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoid = character:FindFirstChildOfClass("Humanoid")

    -- Check if the character and humanoid exist
    if character and humanoid then
        -- Use a variable for BodyEffects and K.O state to avoid repeated calls
        local bodyEffects = character:FindFirstChild("BodyEffects")
        local KOd = bodyEffects and bodyEffects[KOD] and bodyEffects[KOD].Value
        local Grabbed = character:FindFirstChild(GRABBING_CONSTRAINT) ~= nil

        -- Only execute if Anti Stomp is enabled
        if antiStompEnabled and (KOd or Grabbed) then
            -- Prevent interaction by disabling humanoid interactions
            humanoid.PlatformStand = true  -- Disable normal character movements
            humanoid.WalkSpeed = 0  -- Prevent walking
            humanoid.JumpHeight = 0  -- Prevent jumping
            humanoid.Health = 0  -- Force kill the character immediately

            -- Disable collision to make it untouchable by other players
            for _, part in pairs(character:GetChildren()) do
                if part:IsA("BasePart") then
                    part.CanCollide = false  -- Disable collision with other players
                end
            end

            -- Disable unnecessary humanoid states
            humanoid:SetStateEnabled(HumanoidStateType.Physics, false)
            humanoid:SetStateEnabled(HumanoidStateType.Seated, false)
            humanoid:SetStateEnabled(HumanoidStateType.Climbing, false)
            humanoid:SetStateEnabled(HumanoidStateType.Freefall, false)
            humanoid:SetStateEnabled(HumanoidStateType.Ragdoll, false)

            -- Prevent health changes from other players
            humanoid.MaxHealth = humanoid.Health

            -- Clean up BodyEffects to remove any effects causing interaction
            if bodyEffects then
                bodyEffects:ClearAllChildren()
            end

            -- Prevent stomping or any other interaction from players
            local collisionParts = character:GetChildren()
            for _, part in pairs(collisionParts) do
                if part:IsA("BasePart") then
                    part.CanCollide = false  -- Fully prevent collision interactions
                end
            end

            -- Immediately reset the character to remove any potential interaction
            player:LoadCharacter()  -- Reload the character to reset the player
        end
    end
end)


    do
        do
            local oJ = oI["Ragebot"]:AddLeftGroupbox("Targeting")
            local oK = oJ:AddToggle("Targeting_Enable", {Text = "Enable", Default = false})
            oK:AddKeyPicker("Targeting_PickKey", {Default = "Q", Text = "Pick Target", Mode = "Toggle", NoUI = false})
            do
                local oL = oJ:AddDependencyBox()
                oL:AddDropdown(
                    "Targeting_Checks",
                    {
                        Text = "Checks",
                        Values = {"Visible", "Protected", "Knocked", "Dead", "Grabbed"},
                        Default = 0,
                        Multi = true
                    }
                )
                local oM = oL:AddToggle("Targeting_UseList", {Text = "List", Default = false})
                do
                    local oN = oL:AddDependencyBox()
                    oN:AddDropdown(
                        "Targeting_PlayerList",
                        {SpecialType = "Player", Text = "Player", Multi = true, AllowNull = true}
                    )
                    oN:AddDropdown(
                        "Targeting_SwapMode",
                        {Text = "Swap Mode", Values = {"Knocked", "Dead", "10 Seconds"}, Default = 1}
                    )
                    oN:SetupDependencies({{Toggles["Targeting_UseList"], true}})
                end
                local oO = oL:AddToggle("Targeting_AutoSelect", {Text = "Auto Select", Default = false})
                do
                    local oP = oL:AddDependencyBox()
                    local oQ = oP:AddToggle("Targeting_UseFov", {Text = "Use Fov", Default = false})
                    do
                        local oR = oP:AddDependencyBox()
                        oR:AddSlider(
                            "Targeting_FovSize",
                            {Text = "Fov Size", Min = 10, Max = 500, Default = 100, Rounding = 0}
                        )
                        local oS = oR:AddToggle("Targeting_ShowFov", {Text = "Show Fov", Default = false})
                        oS:AddColorPicker(
                            "Targeting_FovGradient1",
                            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 1", Transparency = 0}
                        )
                        oS:AddColorPicker(
                            "Targeting_FovGradient2",
                            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 2", Transparency = 0}
                        )
                        oS:AddColorPicker(
                            "Targeting_FovGradient3",
                            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 3", Transparency = 0}
                        )
                        oS:AddColorPicker(
                            "Targeting_FovGradient4",
                            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 4", Transparency = 0}
                        )
                        oR:SetupDependencies({{Toggles["Targeting_UseFov"], true}})
                    end
                    oP:SetupDependencies({{Toggles["Targeting_AutoSelect"], true}})
                end
                local oT = oL:AddToggle("Targeting_Visualise", {Text = "Visualize", Default = false})
                do
                    local oU = oL:AddDependencyBox()
                    local oV = oU:AddToggle("Targeting_Tracer", {Text = "Tracer", Default = false})
                    oV:AddColorPicker(
                        "Targeting_TracerOutline",
                        {Default = Color3.fromRGB(0, 0, 0), Title = "Outline", Transparency = 0}
                    )
                    oV:AddColorPicker(
                        "Targeting_TracerMain",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Main", Transparency = 0}
                    )
                    do
                        local oW = oU:AddDependencyBox()
                        oW:AddSlider(
                            "Targeting_TracerThickness",
                            {Text = "Thickness", Min = 0.5, Max = 5, Default = 1.5, Rounding = 1}
                        )
                        oW:SetupDependencies({{Toggles["Targeting_Tracer"], true}})
                    end
                    local oX = oU:AddToggle("Targeting_Highlight", {Text = "Highlight", Default = false})
                    oX:AddColorPicker(
                        "Targeting_HighlightFill",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Fill", Transparency = 0.5}
                    )
                    oX:AddColorPicker(
                        "Targeting_HighlightOutline",
                        {Default = Color3.fromRGB(0, 0, 0), Title = "Outline", Transparency = 0}
                    )
                    oU:AddToggle("Targeting_ViewTarget", {Text = "View Target", Default = false})
                    oU:SetupDependencies({{Toggles["Targeting_Visualise"], true}})
                end
                oL:SetupDependencies({{Toggles["Targeting_Enable"], true}})
            end
            do
                local oY = oz["Ragebot_Targeting"]
                local oZ = oz["Ragebot_TargetingFOV"]
                local o_ = oz["Ragebot_TargetingVisualise"]
                if not oY then

                elseif (not oZ or (907 > 3152)) then

                elseif not o_ then

                else
                    local p0 = oY(dL)
                    p0:init()
                    local p1 = oZ(dL)
                    p1:init()
                    local p2 = o_(dL)
                    p2:init()
                    p0:onTargetStateChanged(
                        function(p3)
                            Options["Targeting_PickKey"]["Toggled"] = p3
                            Options["Targeting_PickKey"]:Update()
                        end
                    )
                    local p4 = {currentIndex = 1, lastSwapTime = 0, swapConn = nil}
                    Toggles["Targeting_Enable"]:OnChanged(
                        function()
                            p0:setEnable(Toggles["Targeting_Enable"].Value)
                            if (not Toggles["Targeting_Enable"]["Value"] or (2505 > 4470)) then
                                if p4["swapConn"] then
                                    p4["swapConn"]:Disconnect()
                                    p4["swapConn"] = nil
                                end
                            end
                        end
                    )
                    local function p5(d)
                        if ((type(d) == "string") or (3711 > 4062)) then
                            return dL["players"]:FindFirstChild(d)
                        else
                            return d
                        end
                    end
                    local function p6()
                        local p7 = Options["Targeting_PlayerList"]["Value"]
                        local ku = {}
                        if not p7 then
                            return ku
                        end
                        for d_, eY in pairs(p7) do
                            if eY then
                                local eV = p5(d_)
                                if ((420 == 420) and eV) then
                                    dL.insert(ku, eV)
                                end
                            end
                        end
                        return ku
                    end
                    local function p8(eV)
                        if (eV and eV["Character"]) then
                            dL["targeting"]["target"] = eV["Character"]
                            dL["targeting"]:setupCharacterTracking(eV)
                            p0:updateTargetState()
                            return true
                        else
                            return false
                        end
                    end
                    local function p9()
                        if not dL["targeting"]["target"] then
                            return true
                        end
                        local pa = Options["Targeting_SwapMode"]["Value"]
                        if (dL["targeting"]:checkTargetGrabbed() or (33 >= 3494)) then
                            return true
                        end
                        if (pa == "Knocked") then
                            return dL["targeting"]:checkTargetKnocked()
                        elseif (pa == "Dead") then
                            return dL["targeting"]:checkTargetDead()
                        elseif (pa ~= "10 Seconds") then
                        else
                            local iv = tick()
                            if (((iv - p4["lastSwapTime"]) >= 10) or (1267 == 4744)) then
                                p4["lastSwapTime"] = iv
                                return true
                            end
                        end
                        return false
                    end
                    local function pb(ku)
                        if (#ku == 0) then
                            return
                        end
                        local pc = 0
                        local pd = #ku
                        while pc < pd do
                            p4["currentIndex"] = p4["currentIndex"] + 1
                            if (p4["currentIndex"] <= #ku) then
                            else
                                p4["currentIndex"] = 1
                            end
                            local eV = ku[p4["currentIndex"]]
                            if ((2428 < 3778) and eV and eV["Character"]) then
                                local dS = eV["Character"]
                                if not dS:FindFirstChild("GRABBING_CONSTRAINT") then
                                    if (p8(eV) or (2946 <= 1596)) then
                                        return
                                    end
                                end
                            end
                            pc = pc + 1
                        end
                        dL["targeting"]:resetTarget()
                        p0:updateTargetState()
                    end
                    local function pe()
                        if p4["swapConn"] then
                            p4["swapConn"]:Disconnect()
                            p4["swapConn"] = nil
                        end
                        local ku = p6()
                        if ((4433 > 3127) and (#ku == 0)) then
                            dL["targeting"]:resetTarget()
                            p0:updateTargetState()
                            return
                        end
                        if (#ku ~= 1) then
                        else
                            p8(ku[1])
                            return
                        end
                        p4["currentIndex"] = 0
                        p4["lastSwapTime"] = tick()
                        local pf = false
                        for w = 1, #ku do
                            local eV = ku[w]
                            if (eV and eV["Character"]) then
                                if not eV["Character"]:FindFirstChild("GRABBING_CONSTRAINT") then
                                    p4["currentIndex"] = w
                                    if p8(eV) then
                                        pf = true
                                        break
                                    end
                                end
                            end
                        end
                        if not pf then
                            return
                        end
                        p4["swapConn"] =
                            dL["heart"]:Connect(
                            (
                                newcclosure(
                                    function()
                                        if ((4300 >= 2733) and not Toggles["Targeting_UseList"]["Value"]) then
                                            return
                                        end
                                        if ((4829 == 4829) and not Toggles["Targeting_Enable"]["Value"]) then
                                            return
                                        end
                                        if p9() then
                                            pb(ku)
                                        end
                                    end
                                )
                            )
                        )
                    end
                    Options["Targeting_PlayerList"]:OnChanged(
                        function()
                            if not Toggles["Targeting_UseList"]["Value"] then
                                return
                            end
                            if not Toggles["Targeting_Enable"]["Value"] then
                                return
                            end
                            pe()
                        end
                    )
                    Options["Targeting_SwapMode"]:OnChanged(
                        function()
                            if ((1683 <= 4726) and not Toggles["Targeting_UseList"]["Value"]) then
                                return
                            end
                            if ((4835 >= 3669) and not Toggles["Targeting_Enable"]["Value"]) then
                                return
                            end
                            p4["lastSwapTime"] = tick()
                        end
                    )
                    Toggles["Targeting_UseList"]:OnChanged(
                        function()
                            if Toggles["Targeting_UseList"]["Value"] then
                                if ((2851 > 1859) and Toggles["Targeting_AutoSelect"]["Value"]) then
                                    p0:setAutoSelect(false)
                                end
                                pe()
                            else
                                if ((3848 > 2323) and p4["swapConn"]) then
                                    p4["swapConn"]:Disconnect()
                                    p4["swapConn"] = nil
                                end
                                dL["targeting"]:resetTarget()
                                p0:updateTargetState()
                            end
                        end
                    )
                    Options["Targeting_PickKey"]:OnClick(
                        function()
                            if Toggles["Targeting_UseList"]["Value"] then
                                local ku = p6()
                                if (#ku == 0) then
                                    dL["targeting"]:resetTarget()
                                    p0:updateTargetState()
                                    return
                                end
                                if ((2836 > 469) and dL["targeting"]["target"]) then
                                    if (p4["swapConn"] or (2096 <= 540)) then
                                        p4["swapConn"]:Disconnect()
                                        p4["swapConn"] = nil
                                    end
                                    dL["targeting"]:resetTarget()
                                    p0:updateTargetState()
                                else
                                    pe()
                                end
                            else
                                local eC = {
                                    Friend = true,
                                    Visible = (Options["Targeting_Checks"]["Value"]["Visible"] or false),
                                    Protect = (Options["Targeting_Checks"]["Value"]["Protected"] or false),
                                    KO = (Options["Targeting_Checks"]["Value"]["Knocked"] or false),
                                    Dead = (Options["Targeting_Checks"]["Value"]["Dead"] or false),
                                    Grabbed = (Options["Targeting_Checks"]["Value"]["Grabbed"] or false)
                                }
                                p0:pickTarget(eC)
                                p0:updateTargetState()
                            end
                        end
                    )
                    local function pg()
                        if (not Toggles["Targeting_AutoSelect"]["Value"] or (3183 < 2645)) then
                            return
                        end
                        local eC = {
                            Friend = true,
                            Visible = (Options["Targeting_Checks"]["Value"]["Visible"] or false),
                            Protect = (Options["Targeting_Checks"]["Value"]["Protected"] or false),
                            KO = (Options["Targeting_Checks"]["Value"]["Knocked"] or false),
                            Dead = (Options["Targeting_Checks"]["Value"]["Dead"] or false),
                            Grabbed = (Options["Targeting_Checks"]["Value"]["Grabbed"] or false)
                        }
                        local eF =
                            (Toggles["Targeting_UseFov"]["Value"] and (Options["Targeting_FovSize"]["Value"] / 2)) or
                            nil
                        p0:setAutoSelect(true, eC, eF)
                    end
                    Toggles["Targeting_AutoSelect"]:OnChanged(
                        function()
                            if Toggles["Targeting_AutoSelect"]["Value"] then
                                if Toggles["Targeting_UseList"]["Value"] then
                                    Toggles["Targeting_UseList"]:SetValue(false)
                                end
                                pg()
                            else
                                p0:setAutoSelect(false)
                            end
                        end
                    )
                    Toggles["Targeting_UseFov"]:OnChanged(
                        function()
                            pg()
                        end
                    )
                    Options["Targeting_FovSize"]:OnChanged(
                        function()
                            p1:setSize(Options["Targeting_FovSize"].Value)
                            pg()
                        end
                    )
                    Toggles["Targeting_ShowFov"]:OnChanged(
                        function()
                            p1:setEnable(Toggles["Targeting_ShowFov"].Value)
                        end
                    )
                    Options["Targeting_FovGradient1"]:OnChanged(
                        function()
                            p1:setGradientColor(1, Options["Targeting_FovGradient1"].Value)
                        end
                    )
                    Options["Targeting_FovGradient2"]:OnChanged(
                        function()
                            p1:setGradientColor(2, Options["Targeting_FovGradient2"].Value)
                        end
                    )
                    Options["Targeting_FovGradient3"]:OnChanged(
                        function()
                            p1:setGradientColor(3, Options["Targeting_FovGradient3"].Value)
                        end
                    )
                    Options["Targeting_FovGradient4"]:OnChanged(
                        function()
                            p1:setGradientColor(4, Options["Targeting_FovGradient4"].Value)
                        end
                    )
                    Toggles["Targeting_Tracer"]:OnChanged(
                        function()
                            p2:setTracerEnable(Toggles["Targeting_Tracer"].Value)
                        end
                    )
                    Options["Targeting_TracerOutline"]:OnChanged(
                        function()
                            p2:setOutlineColor(
                                Options["Targeting_TracerOutline"].Value,
                                Options["Targeting_TracerOutline"].Transparency
                            )
                        end
                    )
                    Options["Targeting_TracerMain"]:OnChanged(
                        function()
                            p2:setMainColor(
                                Options["Targeting_TracerMain"].Value,
                                Options["Targeting_TracerMain"].Transparency
                            )
                        end
                    )
                    Options["Targeting_TracerThickness"]:OnChanged(
                        function()
                            p2:setThickness(Options["Targeting_TracerThickness"].Value)
                        end
                    )
                    Toggles["Targeting_Highlight"]:OnChanged(
                        function()
                            p2:setHighlightEnable(Toggles["Targeting_Highlight"].Value)
                        end
                    )
                    Options["Targeting_HighlightFill"]:OnChanged(
                        function()
                            p2:setHighlightFillColor(
                                Options["Targeting_HighlightFill"].Value,
                                Options["Targeting_HighlightFill"].Transparency
                            )
                        end
                    )
                    Options["Targeting_HighlightOutline"]:OnChanged(
                        function()
                            p2:setHighlightOutlineColor(
                                Options["Targeting_HighlightOutline"].Value,
                                Options["Targeting_HighlightOutline"].Transparency
                            )
                        end
                    )
                    Toggles["Targeting_ViewTarget"]:OnChanged(
                        function()
                            p2:setViewTargetEnable(Toggles["Targeting_ViewTarget"].Value)
                        end
                    )
                end
            end
        end
        do
            local ph = oI["Ragebot"]:AddLeftGroupbox("Automatic Shoot")
            local pi = ph:AddToggle("AutoShoot_Enable", {Text = "Enable", Default = false})
            do
                local pj = ph:AddDependencyBox()
                pj:AddSlider(
                    "AutoShoot_Cooldown",
                    {Text = "Shoot Cooldown (ms)", Min = 1, Max = 1000, Default = 1, Rounding = 0}
                )
                local pk =
                    pj:AddDropdown(
                    "AutoShoot_Origin",
                    {Text = "Origin", Values = {"Syncpos", "Upper", "Random"}, Default = 1, Multi = false}
                )
                do
                    local pl = pj:AddDependencyBox()
                    pl:AddSlider(
                        "AutoShoot_UpperDistance",
                        {Text = "Upper Distance", Min = 1, Max = 10, Default = 3, Rounding = 0}
                    )
                    pl:SetupDependencies({{Options["AutoShoot_Origin"], "Upper"}})
                end
                pj:SetupDependencies({{Toggles["AutoShoot_Enable"], true}})
            end
            do
                local pm = oz["Ragebot_AutoShoot"]
                if not pm then

                else
                    local pn = pm(dL)
                    pn:init()
                    pn:setShootCooldown(Options["AutoShoot_Cooldown"].Value)
                    pn:setOriginMode(Options["AutoShoot_Origin"].Value)
                    pn:setUpperDistance(Options["AutoShoot_UpperDistance"].Value)
                    Toggles["AutoShoot_Enable"]:OnChanged(
                        function()
                            pn:setEnable(Toggles["AutoShoot_Enable"].Value)
                        end
                    )
                    Options["AutoShoot_Cooldown"]:OnChanged(
                        function()
                            pn:setShootCooldown(Options["AutoShoot_Cooldown"].Value)
                        end
                    )
                    Options["AutoShoot_Origin"]:OnChanged(
                        function()
                            pn:setOriginMode(Options["AutoShoot_Origin"].Value)
                        end
                    )
                    Options["AutoShoot_UpperDistance"]:OnChanged(
                        function()
                            pn:setUpperDistance(Options["AutoShoot_UpperDistance"].Value)
                        end
                    )
                end
            end
        end
        local po = nil
        do
            local pp = oI["Ragebot"]:AddLeftGroupbox("Multiple Guns")
            local pq = pp:AddToggle("MultiGuns_Enable", {Text = "Enable", Default = false})
            do
                local pr = pp:AddDependencyBox()
                pr:AddDropdown(
                    "MultiGuns_SelectedGuns",
                    {
                        Text = "Guns",
                        Values = {
                            "[AUG]",
                            "[Rifle]",
                            "[LMG]",
                            "[P90]",
                            "[Flintlock]",
                            "[Revolver]",
                            "[Double-Barrel SG]",
                            "[AK47]",
                            "[TacticalShotgun]",
                            "[Shotgun]",
                            "[SMG]",
                            "[DrumGun]",
                            "[Glock]",
                            "[Silencer]",
                            "[AR]"
                        },
                        Default = 0,
                        Multi = true
                    }
                )
                pr:SetupDependencies({{Toggles["MultiGuns_Enable"], true}})
            end
            do
                local ps = oz["Ragebot_MultiGuns"]
                if ((3230 <= 3760) and not ps) then

                else
                    po = ps(dL)
                    po:init()
                    Toggles["MultiGuns_Enable"]:OnChanged(
                        function()
                            po:setEnable(Toggles["MultiGuns_Enable"].Value)
                        end
                    )
                    Options["MultiGuns_SelectedGuns"]:OnChanged(
                        function()
                            local pt = {}
                            for fB, eY in pairs(Options["MultiGuns_SelectedGuns"].Value) do
                                if eY then
                                    table.insert(pt, fB)
                                end
                            end
                            po:setSelectedGuns(pt)
                        end
                    )
                end
            end
        end
        do
            local pu = oI["Ragebot"]:AddRightGroupbox("Desync")
            local pv = pu:AddToggle("Desync_Enable", {Text = "Enable", Default = false})
            do
                local pw = pu:AddDependencyBox()
                local oT = pw:AddToggle("Desync_Visualise", {Text = "Visualise", Default = false})
                do
                    local oU = pw:AddDependencyBox()
                    local oV = oU:AddToggle("Desync_Tracer", {Text = "Tracer", Default = false})
                    oV:AddColorPicker(
                        "Desync_TracerOutline",
                        {Default = Color3.fromRGB(0, 0, 0), Title = "Outline", Transparency = 0}
                    )
                    oV:AddColorPicker(
                        "Desync_TracerMain",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Main", Transparency = 0}
                    )
                    local px = oU:AddToggle("Desync_Dummy", {Text = "Dummy", Default = false})
                    px:AddColorPicker(
                        "Desync_DummyColor",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Color", Transparency = 0.7}
                    )
                    do
                        local py = oU:AddDependencyBox()
                        py:AddDropdown("Desync_DummyType", {Text = "Type", Default = 1, Values = {"R6", "Clone"}})
                        py:SetupDependencies({{Toggles["Desync_Dummy"], true}})
                    end
                    local pz = oU:AddToggle("Desync_Image", {Text = "Image", Default = false})
                    pz:AddColorPicker(
                        "Desync_ImageColor",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Color", Transparency = 0.7}
                    )
                    do
                        local pA = oU:AddDependencyBox()
                        pA:AddSlider(
                            "Desync_ImageScale",
                            {Text = "Scale", Min = 0.5, Max = 5, Default = 1, Rounding = 1, Suffix = "x"}
                        )
                        pA:SetupDependencies({{Toggles["Desync_Image"], true}})
                    end
                    oU:SetupDependencies({{Toggles["Desync_Visualise"], true}})
                end
                local pB = pw:AddToggle("Desync_VoidHide", {Text = "Void Hide", Default = false})
                do
                    local pC = pw:AddDependencyBox()
                    pC:AddDropdown(
                        "Desync_VoidHidePattern",
                        {Text = "Pattern", Values = {"Deep Void", "Break Null"}, Default = 1}
                    )
                    do
                        local pD = pC:AddDependencyBox()
                        pD:AddDropdown(
                            "Desync_VoidHideDeepDirection",
                            {Text = "Direction", Values = {"+Y", "-Y", "+Z", "-Z", "+X", "-X"}, Default = 2}
                        )
                        pD:AddSlider(
                            "Desync_VoidHideDeepSpeed",
                            {Text = "Switch Speed", Min = 0.01, Max = 0.5, Default = 0.05, Rounding = 2, Suffix = "s"}
                        )
                        pD:AddSlider(
                            "Desync_VoidHideDepthMult",
                            {Text = "Depth Multiplier", Min = 1, Max = 50, Default = 1, Rounding = 1, Suffix = "x"}
                        )
                        pD:SetupDependencies({{Options["Desync_VoidHidePattern"], "Deep Void"}})
                    end
                    do
                        local pE = pC:AddDependencyBox()
                        pE:AddDropdown(
                            "Desync_VoidHideBreakDirection",
                            {Text = "Direction", Values = {"+Y", "-Y", "+Z", "-Z", "+X", "-X"}, Default = 2}
                        )
                        pE:AddSlider(
                            "Desync_VoidHideBreakSpeed",
                            {Text = "Switch Speed", Min = 0.01, Max = 0.5, Default = 0.05, Rounding = 2, Suffix = "s"}
                        )
                        pE:SetupDependencies({{Options["Desync_VoidHidePattern"], "Break Null"}})
                    end
                    pC:SetupDependencies({{Toggles["Desync_VoidHide"], true}})
                end
                local pF = pw:AddToggle("Desync_VoidReload", {Text = "Void Reload", Default = false})
                do
                    local pG = pw:AddDependencyBox()
                    pG:AddDropdown(
                        "Desync_VoidReloadDirection",
                        {Text = "Direction", Values = {"+Y", "-Y", "+Z", "-Z", "+X", "-X"}, Default = 2}
                    )
                    pG:AddSlider(
                        "Desync_VoidReloadSpeed",
                        {Text = "Switch Speed", Min = 0.01, Max = 0.5, Default = 0.05, Rounding = 2, Suffix = "s"}
                    )
                    pG:SetupDependencies({{Toggles["Desync_VoidReload"], true}})
                end
                local pH = pw:AddToggle("Desync_AutoBuy", {Text = "AutoBuy", Default = false})
                do
                    local pI = pw:AddDependencyBox()
                    pI:AddDropdown(
                        "Desync_AutoBuyOptions",
                        {Text = "Options", Values = {"Armor", "Guns", "Ammo"}, Default = 0, Multi = true}
                    )
                    pI:AddDropdown(
                        "Desync_AutoBuyGuns",
                        {
                            Text = "Guns",
                            Values = {
                                "[Rifle]",
                                "[LMG]",
                                "[P90]",
                                "[Flintlock]",
                                "[Revolver]",
                                "[Double-Barrel SG]",
                                "[AK47]",
                                "[TacticalShotgun]",
                                "[SMG]",
                                "[AR]",
                                "[Silencer]",
                                "[Shotgun]",
                                "[AUG]"
                            },
                            Default = 0,
                            Multi = true
                        }
                    )
                    pI:AddDropdown(
                        "Desync_AutoBuyConditions",
                        {
                            Text = "Don't Buy If",
                            Values = {"No Target", "Target Alive", "Target Forcefielded"},
                            Default = 0,
                            Multi = true
                        }
                    )
                    pI:SetupDependencies({{Toggles["Desync_AutoBuy"], true}})
                end
                local pJ = pw:AddToggle("Desync_AutoStomp", {Text = "Auto Stomp", Default = false})
                do
                    local pK = pw:AddDependencyBox()
                    pK:AddSlider(
                        "Desync_AutoStompHeight",
                        {Text = "Stomp Height", Min = 1, Max = 5, Default = 2.7, Rounding = 1, Suffix = "s"}
                    )
                    pK:SetupDependencies({{Toggles["Desync_AutoStomp"], true}})
                end
                local pL = pw:AddToggle("Desync_CSync", {Text = "Follow target", Default = false})
                do
                    local pM = pw:AddDependencyBox()
                    pM:AddDropdown(
                        "Desync_CSyncMode",
                        {
                            Text = "Mode",
                            Values = {"Random", "Spiral", "SpiralYZ", "SpiralYX", "BaitSpiral"},
                            Default = 1,
                            Multi = false
                        }
                    )
                    do
                        local pN = pM:AddDependencyBox()
                        pN:AddSlider(
                            "Desync_CSyncRadiusX",
                            {Text = "Radius X", Min = 0, Max = 100, Default = 5, Rounding = 2}
                        )
                        pN:AddSlider(
                            "Desync_CSyncRadiusY",
                            {Text = "Radius Y", Min = 0, Max = 100, Default = 5, Rounding = 2}
                        )
                        pN:AddSlider(
                            "Desync_CSyncRadiusZ",
                            {Text = "Radius Z", Min = 0, Max = 100, Default = 5, Rounding = 2}
                        )
                        pN:AddToggle("Desync_CSyncMinDistance", {Text = "Filter Min Distance", Default = false})
                        do
                            local pO = pN:AddDependencyBox()
                            pO:AddSlider(
                                "Desync_CSyncMinDistX",
                                {Text = "Min Distance X", Min = 0, Max = 100, Default = 0, Rounding = 0}
                            )
                            pO:AddSlider(
                                "Desync_CSyncMinDistY",
                                {Text = "Min Distance Y", Min = 0, Max = 100, Default = 0, Rounding = 0}
                            )
                            pO:AddSlider(
                                "Desync_CSyncMinDistZ",
                                {Text = "Min Distance Z", Min = 0, Max = 100, Default = 0, Rounding = 0}
                            )
                            pO:SetupDependencies({{Toggles["Desync_CSyncMinDistance"], true}})
                        end
                        pN:SetupDependencies({{Options["Desync_CSyncMode"], "Random"}})
                    end
                    do
                        local pP = pM:AddDependencyBox()
                        pP:AddSlider(
                            "Desync_CSyncSpiralDistance",
                            {Text = "Distance", Min = -100, Max = 100, Default = 10, Rounding = 2}
                        )
                        pP:AddSlider(
                            "Desync_CSyncSpiralSpeed",
                            {Text = "Speed", Min = 0, Max = 1500, Default = 300, Rounding = 0}
                        )
                        pP:AddSlider(
                            "Desync_CSyncSpiralYOffset",
                            {Text = "Y Offset", Min = -20, Max = 20, Default = 0, Rounding = 2}
                        )
                        pP:SetupDependencies({{Options["Desync_CSyncMode"], "Spiral"}})
                    end
                    do
                        local pQ = pM:AddDependencyBox()
                        pQ:AddSlider(
                            "Desync_CSyncSpiralYZDistance",
                            {Text = "Distance", Min = -100, Max = 100, Default = 10, Rounding = 2}
                        )
                        pQ:AddSlider(
                            "Desync_CSyncSpiralYZSpeed",
                            {Text = "Speed", Min = 0, Max = 1500, Default = 300, Rounding = 0}
                        )
                        pQ:AddSlider(
                            "Desync_CSyncSpiralYZXOffset",
                            {Text = "X Offset", Min = -20, Max = 20, Default = 0, Rounding = 2}
                        )
                        pQ:SetupDependencies({{Options["Desync_CSyncMode"], "SpiralYZ"}})
                    end
                    do
                        local pR = pM:AddDependencyBox()
                        pR:AddSlider(
                            "Desync_CSyncSpiralYXDistance",
                            {Text = "Distance", Min = -100, Max = 100, Default = 10, Rounding = 2}
                        )
                        pR:AddSlider(
                            "Desync_CSyncSpiralYXSpeed",
                            {Text = "Speed", Min = 0, Max = 1500, Default = 300, Rounding = 0}
                        )
                        pR:AddSlider(
                            "Desync_CSyncSpiralYXZOffset",
                            {Text = "Z Offset", Min = -20, Max = 20, Default = 0, Rounding = 2}
                        )
                        pR:SetupDependencies({{Options["Desync_CSyncMode"], "SpiralYX"}})
                    end
                    do
                        local pS = pM:AddDependencyBox()
                        pS:AddSlider(
                            "Desync_CSyncBaitSpiralDistance",
                            {Text = "Spiral Distance", Min = -100, Max = 100, Default = 10, Rounding = 2}
                        )
                        pS:AddSlider(
                            "Desync_CSyncBaitSpiralSpeed",
                            {Text = "Spiral Speed", Min = 0, Max = 1500, Default = 300, Rounding = 0}
                        )
                        pS:AddSlider(
                            "Desync_CSyncBaitSpiralYOffset",
                            {Text = "Y Offset", Min = -20, Max = 20, Default = 0, Rounding = 2}
                        )
                        pS:AddSlider(
                            "Desync_CSyncBaitCooldown",
                            {Text = "Bait Cooldown", Min = 0.1, Max = 1, Default = 0.5, Rounding = 2}
                        )
                        pS:AddSlider(
                            "Desync_CSyncBaitDistance",
                            {Text = "Bait Distance", Min = 100, Max = 1500, Default = 100, Rounding = 1}
                        )
                        pS:AddSlider(
                            "Desync_CSyncBaitWait",
                            {Text = "Bait Wait", Min = 0, Max = 1, Default = 0.1, Rounding = 2}
                        )
                        pS:AddDropdown(
                            "Desync_CSyncBaitDirections",
                            {Text = "Bait Directions", Values = {"X", "Y", "Z"}, Default = 0, Multi = true}
                        )
                        pS:SetupDependencies({{Options["Desync_CSyncMode"], "BaitSpiral"}})
                    end
                    local pT = pM:AddToggle("Desync_CSyncPredictEnable", {Text = "Predict Pos", Default = false})
                    do
                        local pU = pM:AddDependencyBox()
                        pU:AddDropdown(
                            "Desync_CSyncPredictMode",
                            {Text = "Mode", Values = {"Regular", "Calculate", "Better"}, Default = 1, Multi = false}
                        )
                        do
                            local pV = pU:AddDependencyBox()
                            pV:AddSlider(
                                "Desync_CSyncPredictStrength",
                                {Text = "Prediction Strength", Min = 1, Max = 2000, Default = 100, Rounding = 0}
                            )
                            pV:AddToggle("Desync_CSyncResolveEnable", {Text = "Resolve", Default = false})
                            do
                                local pW = pV:AddDependencyBox()
                                pW:AddSlider(
                                    "Desync_CSyncResolveAggression",
                                    {Text = "Resolve Aggression", Min = 0.1, Max = 10, Default = 1, Rounding = 1}
                                )
                                pW:SetupDependencies({{Toggles["Desync_CSyncResolveEnable"], true}})
                            end
                            pV:SetupDependencies({{Options["Desync_CSyncPredictMode"], "Regular"}})
                        end
                        do
                            local pX = pU:AddDependencyBox()
                            pX:AddSlider(
                                "Desync_CSyncCalculateHistorySize",
                                {Text = "Calculate Rate", Min = 60, Max = 500, Default = 60, Rounding = 0}
                            )
                            pX:AddSlider(
                                "Desync_CSyncCalculateVelWeight",
                                {Text = "Velocity Multiplier", Min = 0.5, Max = 5, Default = 1, Rounding = 2}
                            )
                            pX:AddSlider(
                                "Desync_CSyncCalculateAccWeight",
                                {Text = "Bonus Multiplier", Min = 0, Max = 3, Default = 0.35, Rounding = 2}
                            )
                            pX:AddSlider(
                                "Desync_CSyncCalculateAdaptRate",
                                {Text = "Refresh Rate", Min = 0.01, Max = 10, Default = 2, Rounding = 2}
                            )
                            pX:SetupDependencies({{Options["Desync_CSyncPredictMode"], "Calculate"}})
                        end
                        do
                            local pY = pU:AddDependencyBox()
                            pY:AddSlider(
                                "Desync_CSyncBetterPingDivision",
                                {Text = "ping factor", Min = 1, Max = 1000, Default = 500, Rounding = 0}
                            )
                            pY:SetupDependencies({{Options["Desync_CSyncPredictMode"], "Better"}})
                        end
                        pU:SetupDependencies({{Toggles["Desync_CSyncPredictEnable"], true}})
                    end
                    pM:SetupDependencies({{Toggles["Desync_CSync"], true}})
                end
                pw:SetupDependencies({{Toggles["Desync_Enable"], true}})
            end
            do
                local pZ = oz["Ragebot_DesyncVisualise"]
                if not pZ then

                    return
                end
                local p_ = pZ(dL)
                p_:init()
                p_:setDesyncApi(dL.desync)
                Toggles["Desync_Enable"]:OnChanged(
                    function()
                        if Toggles["Desync_Enable"]["Value"] then
                            dL["desync"]:syncWithPlayer()
                        else
                            dL["desync"]:stop()
                            if Toggles["Desync_Tracer"]["Value"] then
                                Toggles["Desync_Tracer"]:SetValue(false)
                            end
                            if ((3828 == 3828) and Toggles["Desync_Dummy"]["Value"]) then
                                Toggles["Desync_Dummy"]:SetValue(false)
                            end
                            if ((554 == 554) and Toggles["Desync_Image"]["Value"]) then
                                Toggles["Desync_Image"]:SetValue(false)
                            end
                            p_:stopLoop()
                        end
                    end
                )
                Toggles["Desync_Tracer"]:OnChanged(
                    function()
                        p_:setTracerEnable(Toggles["Desync_Tracer"].Value)
                    end
                )
                Options["Desync_TracerOutline"]:OnChanged(
                    function()
                        p_:setOutlineColor(
                            Options["Desync_TracerOutline"].Value,
                            Options["Desync_TracerOutline"].Transparency
                        )
                    end
                )
                Options["Desync_TracerMain"]:OnChanged(
                    function()
                        p_:setMainColor(Options["Desync_TracerMain"].Value, Options["Desync_TracerMain"].Transparency)
                    end
                )
                Toggles["Desync_Dummy"]:OnChanged(
                    function()
                        p_:setDummyEnable(Toggles["Desync_Dummy"].Value)
                    end
                )
                Options["Desync_DummyType"]:OnChanged(
                    function()
                        p_:setDummyType(Options["Desync_DummyType"].Value)
                    end
                )
                Options["Desync_DummyColor"]:OnChanged(
                    function()
                        p_:setDummyColor(Options["Desync_DummyColor"].Value, Options["Desync_DummyColor"].Transparency)
                    end
                )
                Toggles["Desync_Image"]:OnChanged(
                    function()
                        p_:setImageEnable(Toggles["Desync_Image"].Value)
                    end
                )
                Options["Desync_ImageColor"]:OnChanged(
                    function()
                        p_:setImageColor(Options["Desync_ImageColor"].Value, Options["Desync_ImageColor"].Transparency)
                    end
                )
                Options["Desync_ImageScale"]:OnChanged(
                    function()
                        p_:setImageScale(Options["Desync_ImageScale"].Value)
                    end
                )
            end
            do
                local q0 = oz["Ragebot_DesyncAutoBuy"]
                local q1 = oz["Ragebot_DesyncVoidHide"]
                local q2 = oz["Ragebot_DesyncVoidReload"]
                local q3 = oz["Ragebot_DesyncAutoStomp"]
                local q4 = oz["Ragebot_DesyncCSync"]
                if (not q0 or (2563 == 172)) then

                    return
                end
                if not q1 then

                    return
                end
                if not q2 then

                    return
                end
                if ((3889 >= 131) and not q3) then

                    return
                end
                if (not q4 or (492 == 4578)) then

                    return
                end
                local q5 = q0(dL)
                q5:init()
                if po then
                    po:setAutoBuyModule(q5)
                end
                local q6 = q3(dL)
                q6:init()
                local q7 = q4(dL)
                q7:init()
                q7:setAutoBuyModule(q5)
                q7:setAutoStompModule(q6)
                local q8 = q2(dL)
                q8:init()
                q8:setAutoBuyModule(q5)
                local q9 = q1(dL)
                q9:init()
                q9:setAutoBuyModule(q5)
                q9:setVoidReloadModule(q8)
                q9:setAutoStompModule(q6)
                q9:setCSyncModule(q7)
                Toggles["Desync_AutoBuy"]:OnChanged(
                    function()
                        q5:setEnable(Toggles["Desync_AutoBuy"].Value)
                    end
                )
                Options["Desync_AutoBuyOptions"]:OnChanged(
                    function()
                        local nS = Options["Desync_AutoBuyOptions"]["Value"]
                        q5:setArmorEnable(nS["Armor"] or false)
                        q5:setGunsEnable(nS["Guns"] or false)
                        q5:setAmmoEnable(nS["Ammo"] or false)
                    end
                )
                Options["Desync_AutoBuyGuns"]:OnChanged(
                    function()
                        local pt = {}
                        for fB, eY in pairs(Options["Desync_AutoBuyGuns"].Value) do
                            if eY then
                                dL.insert(pt, fB)
                            end
                        end
                        q5:setSelectedGuns(pt)
                    end
                )
                Options["Desync_AutoBuyConditions"]:OnChanged(
                    function()
                        local fL = Options["Desync_AutoBuyConditions"]["Value"]
                        q5:setConditions(
                            {
                                noTarget = (fL["No Target"] or false),
                                targetAlive = (fL["Target Alive"] or false),
                                targetForcefielded = (fL["Target Forcefielded"] or false)
                            }
                        )
                    end
                )
                Toggles["Desync_VoidHide"]:OnChanged(
                    function()
                        q9:setEnable(Toggles["Desync_VoidHide"].Value)
                    end
                )
                Options["Desync_VoidHidePattern"]:OnChanged(
                    function()
                        q9:setPattern(Options["Desync_VoidHidePattern"].Value)
                    end
                )
                Options["Desync_VoidHideDeepDirection"]:OnChanged(
                    function()
                        q9:setDeepDirection(Options["Desync_VoidHideDeepDirection"].Value)
                    end
                )
                Options["Desync_VoidHideDeepSpeed"]:OnChanged(
                    function()
                        q9:setDeepSwitchSpeed(Options["Desync_VoidHideDeepSpeed"].Value)
                    end
                )
                Options["Desync_VoidHideDepthMult"]:OnChanged(
                    function()
                        q9:setDepthMultiplier(Options["Desync_VoidHideDepthMult"].Value)
                    end
                )
                Options["Desync_VoidHideBreakDirection"]:OnChanged(
                    function()
                        q9:setBreakDirection(Options["Desync_VoidHideBreakDirection"].Value)
                    end
                )
                Options["Desync_VoidHideBreakSpeed"]:OnChanged(
                    function()
                        q9:setBreakSwitchSpeed(Options["Desync_VoidHideBreakSpeed"].Value)
                    end
                )
                Toggles["Desync_VoidReload"]:OnChanged(
                    function()
                        q8:setEnable(Toggles["Desync_VoidReload"].Value)
                    end
                )
                Options["Desync_VoidReloadDirection"]:OnChanged(
                    function()
                        q8:setBreakDirection(Options["Desync_VoidReloadDirection"].Value)
                    end
                )
                Options["Desync_VoidReloadSpeed"]:OnChanged(
                    function()
                        q8:setBreakSwitchSpeed(Options["Desync_VoidReloadSpeed"].Value)
                    end
                )
                Toggles["Desync_AutoStomp"]:OnChanged(
                    function()
                        q6:setEnable(Toggles["Desync_AutoStomp"].Value)
                    end
                )
                Options["Desync_AutoStompHeight"]:OnChanged(
                    function()
                        q6:setStompHeight(Options["Desync_AutoStompHeight"].Value)
                    end
                )
                Toggles["Desync_CSync"]:OnChanged(
                    function()
                        q7:setEnable(Toggles["Desync_CSync"].Value)
                    end
                )
                Options["Desync_CSyncMode"]:OnChanged(
                    function()
                        q7:setMode(Options["Desync_CSyncMode"].Value)
                    end
                )
                Options["Desync_CSyncRadiusX"]:OnChanged(
                    function()
                        q7:setRadiusX(Options["Desync_CSyncRadiusX"].Value)
                    end
                )
                Options["Desync_CSyncRadiusY"]:OnChanged(
                    function()
                        q7:setRadiusY(Options["Desync_CSyncRadiusY"].Value)
                    end
                )
                Options["Desync_CSyncRadiusZ"]:OnChanged(
                    function()
                        q7:setRadiusZ(Options["Desync_CSyncRadiusZ"].Value)
                    end
                )
                Toggles["Desync_CSyncMinDistance"]:OnChanged(
                    function()
                        q7:setUseMinDistance(Toggles["Desync_CSyncMinDistance"].Value)
                    end
                )
                Options["Desync_CSyncMinDistX"]:OnChanged(
                    function()
                        q7:setMinDistanceX(Options["Desync_CSyncMinDistX"].Value)
                    end
                )
                Options["Desync_CSyncMinDistY"]:OnChanged(
                    function()
                        q7:setMinDistanceY(Options["Desync_CSyncMinDistY"].Value)
                    end
                )
                Options["Desync_CSyncMinDistZ"]:OnChanged(
                    function()
                        q7:setMinDistanceZ(Options["Desync_CSyncMinDistZ"].Value)
                    end
                )
                Options["Desync_CSyncSpiralDistance"]:OnChanged(
                    function()
                        q7:setSpiralDistance(Options["Desync_CSyncSpiralDistance"].Value)
                    end
                )
                Options["Desync_CSyncSpiralSpeed"]:OnChanged(
                    function()
                        q7:setSpiralSpeed(Options["Desync_CSyncSpiralSpeed"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYOffset"]:OnChanged(
                    function()
                        q7:setSpiralYOffset(Options["Desync_CSyncSpiralYOffset"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYZDistance"]:OnChanged(
                    function()
                        q7:setSpiralYZDistance(Options["Desync_CSyncSpiralYZDistance"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYZSpeed"]:OnChanged(
                    function()
                        q7:setSpiralYZSpeed(Options["Desync_CSyncSpiralYZSpeed"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYZXOffset"]:OnChanged(
                    function()
                        q7:setSpiralYZXOffset(Options["Desync_CSyncSpiralYZXOffset"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYXDistance"]:OnChanged(
                    function()
                        q7:setSpiralYXDistance(Options["Desync_CSyncSpiralYXDistance"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYXSpeed"]:OnChanged(
                    function()
                        q7:setSpiralYXSpeed(Options["Desync_CSyncSpiralYXSpeed"].Value)
                    end
                )
                Options["Desync_CSyncSpiralYXZOffset"]:OnChanged(
                    function()
                        q7:setSpiralYXZOffset(Options["Desync_CSyncSpiralYXZOffset"].Value)
                    end
                )
                Options["Desync_CSyncBaitSpiralDistance"]:OnChanged(
                    function()
                        q7:setBaitSpiralDistance(Options["Desync_CSyncBaitSpiralDistance"].Value)
                    end
                )
                Options["Desync_CSyncBaitSpiralSpeed"]:OnChanged(
                    function()
                        q7:setBaitSpiralSpeed(Options["Desync_CSyncBaitSpiralSpeed"].Value)
                    end
                )
                Options["Desync_CSyncBaitSpiralYOffset"]:OnChanged(
                    function()
                        q7:setBaitSpiralYOffset(Options["Desync_CSyncBaitSpiralYOffset"].Value)
                    end
                )
                Options["Desync_CSyncBaitCooldown"]:OnChanged(
                    function()
                        q7:setBaitCooldown(Options["Desync_CSyncBaitCooldown"].Value)
                    end
                )
                Options["Desync_CSyncBaitDistance"]:OnChanged(
                    function()
                        q7:setBaitDistance(Options["Desync_CSyncBaitDistance"].Value)
                    end
                )
                Options["Desync_CSyncBaitWait"]:OnChanged(
                    function()
                        q7:setBaitWait(Options["Desync_CSyncBaitWait"].Value)
                    end
                )
                Options["Desync_CSyncBaitDirections"]:OnChanged(
                    function()
                        q7:setBaitDirections(Options["Desync_CSyncBaitDirections"].Value)
                    end
                )
                Toggles["Desync_CSyncPredictEnable"]:OnChanged(
                    function()
                        q7:setPredictEnable(Toggles["Desync_CSyncPredictEnable"].Value)
                    end
                )
                Options["Desync_CSyncPredictMode"]:OnChanged(
                    function()
                        q7:setPredictMode(Options["Desync_CSyncPredictMode"].Value)
                    end
                )
                Options["Desync_CSyncPredictStrength"]:OnChanged(
                    function()
                        q7:setPredictStrength(Options["Desync_CSyncPredictStrength"].Value)
                    end
                )
                Toggles["Desync_CSyncResolveEnable"]:OnChanged(
                    function()
                        q7:setResolveEnable(Toggles["Desync_CSyncResolveEnable"].Value)
                    end
                )
                Options["Desync_CSyncResolveAggression"]:OnChanged(
                    function()
                        q7:setResolveAggression(Options["Desync_CSyncResolveAggression"].Value)
                    end
                )
                Options["Desync_CSyncCalculateHistorySize"]:OnChanged(
                    function()
                        q7:setCalculateHistorySize(Options["Desync_CSyncCalculateHistorySize"].Value)
                    end
                )
                Options["Desync_CSyncCalculateVelWeight"]:OnChanged(
                    function()
                        q7:setCalculateVelWeight(Options["Desync_CSyncCalculateVelWeight"].Value)
                    end
                )
                Options["Desync_CSyncCalculateAccWeight"]:OnChanged(
                    function()
                        q7:setCalculateAccWeight(Options["Desync_CSyncCalculateAccWeight"].Value)
                    end
                )
                Options["Desync_CSyncCalculateAdaptRate"]:OnChanged(
                    function()
                        q7:setCalculateAdaptRate(Options["Desync_CSyncCalculateAdaptRate"].Value)
                    end
                )
                Options["Desync_CSyncBetterPingDivision"]:OnChanged(
                    function()
                        q7:setBetterPingDivisionFactor(Options["Desync_CSyncBetterPingDivision"].Value)
                    end
                )
            end
        end
    end






    do
        do
            local qa = oI["Visuals"]:AddLeftGroupbox("Self Chams")
            do
                local qb = oz["Visuals_SelfChams"]
                if (not qb or (4112 < 1816)) then

                    return
                end
                local qc = qb(dL)
                qc:init()
                local qd = qa:AddToggle("SelfChams_Enable", {Text = "Enable", Default = false})
                qd:AddColorPicker(
                    "SelfChams_Color",
                    {Default = Color3.fromRGB(155, 125, 175), Title = "Chams Color", Transparency = 0}
                )
                qd:AddColorPicker(
                    "SelfChams_ParticleColor",
                    {Default = Color3.fromRGB(255, 255, 255), Title = "Particle Color", Transparency = 0}
                )
                do
                    local qe = qa:AddDependencyBox()
                    qe:AddDropdown(
                        "SelfChams_Material",
                        {Text = "Material", Default = 1, Values = {"Neon", "Glass", "ForceField"}}
                    )
                    qe:AddDropdown(
                        "SelfChams_Add",
                        {Text = "Add", Default = 1, Values = {"None", "Stars", "Particles", "Smoke", "Lighting"}}
                    )
                    qe:SetupDependencies({{Toggles["SelfChams_Enable"], true}})
                end
                Toggles["SelfChams_Enable"]:OnChanged(
                    function()
                        qc:setEnable(Toggles["SelfChams_Enable"].Value)
                    end
                )
                Options["SelfChams_Color"]:OnChanged(
                    function()
                        qc:setColor(Options["SelfChams_Color"].Value, Options["SelfChams_Color"].Transparency)
                    end
                )
                Options["SelfChams_ParticleColor"]:OnChanged(
                    function()
                        qc:setParticleColor(
                            Options["SelfChams_ParticleColor"].Value,
                            Options["SelfChams_ParticleColor"].Transparency
                        )
                    end
                )
                Options["SelfChams_Material"]:OnChanged(
                    function()
                        qc:setMaterial(Options["SelfChams_Material"].Value)
                    end
                )
                Options["SelfChams_Add"]:OnChanged(
                    function()
                        qc:setAdd(Options["SelfChams_Add"].Value)
                    end
                )
            end
        end
        do
            local qf = oI["Visuals"]:AddRightGroupbox("Gun Chams")
            do
                local qg = oz["Visuals_GunChams"]
                if not qg then

                    return
                end
                local qh = qg(dL)
                qh:init()
                local qi = qf:AddToggle("GunChams_Enable", {Text = "Enable", Default = false})
                qi:AddColorPicker(
                    "GunChams_Color",
                    {Default = Color3.fromRGB(155, 125, 175), Title = "Chams Color", Transparency = 0}
                )
                qi:AddColorPicker(
                    "GunChams_ParticleColor",
                    {Default = Color3.fromRGB(255, 255, 255), Title = "Particle Color", Transparency = 0}
                )
                do
                    local qj = qf:AddDependencyBox()
                    qj:AddDropdown(
                        "GunChams_Material",
                        {Text = "Material", Default = 1, Values = {"Neon", "Glass", "ForceField"}}
                    )
                    qj:AddDropdown(
                        "GunChams_Add",
                        {Text = "Add", Default = 1, Values = {"None", "Stars", "Particles", "Smoke", "Lighting"}}
                    )
                    qj:SetupDependencies({{Toggles["GunChams_Enable"], true}})
                end
                Toggles["GunChams_Enable"]:OnChanged(
                    function()
                        qh:setEnable(Toggles["GunChams_Enable"].Value)
                    end
                )
                Options["GunChams_Color"]:OnChanged(
                    function()
                        qh:setColor(Options["GunChams_Color"].Value, Options["GunChams_Color"].Transparency)
                    end
                )
                Options["GunChams_ParticleColor"]:OnChanged(
                    function()
                        qh:setParticleColor(
                            Options["GunChams_ParticleColor"].Value,
                            Options["GunChams_ParticleColor"].Transparency
                        )
                    end
                )
                Options["GunChams_Material"]:OnChanged(
                    function()
                        qh:setMaterial(Options["GunChams_Material"].Value)
                    end
                )
                Options["GunChams_Add"]:OnChanged(
                    function()
                        qh:setAdd(Options["GunChams_Add"].Value)
                    end
                )
            end
        end
        do
            local qk = oI["Visuals"]:AddLeftGroupbox("Highlights")
            do
                local ql = oz["Visuals_Highlights"]
                if ((4525 >= 1223) and not ql) then

                    return
                end
                local qm = ql(dL)
                qm:init()
                local qn = qk:AddToggle("Highlights_Self", {Text = "Self", Default = false})
                qn:AddColorPicker(
                    "Highlights_SelfFill",
                    {Default = Color3.fromRGB(255, 255, 255), Title = "Fill", Transparency = 0.5}
                )
                qn:AddColorPicker(
                    "Highlights_SelfOutline",
                    {Default = Color3.fromRGB(0, 0, 0), Title = "Outline", Transparency = 0}
                )
                local qo = qk:AddToggle("Highlights_Others", {Text = "Others", Default = false})
                qo:AddColorPicker(
                    "Highlights_OthersFill",
                    {Default = Color3.fromRGB(255, 255, 255), Title = "Fill", Transparency = 0.5}
                )
                qo:AddColorPicker(
                    "Highlights_OthersOutline",
                    {Default = Color3.fromRGB(0, 0, 0), Title = "Outline", Transparency = 0}
                )
                Toggles["Highlights_Self"]:OnChanged(
                    function()
                        qm:setSelfEnable(Toggles["Highlights_Self"].Value)
                    end
                )
                Toggles["Highlights_Others"]:OnChanged(
                    function()
                        qm:setOthersEnable(Toggles["Highlights_Others"].Value)
                    end
                )
                Options["Highlights_SelfFill"]:OnChanged(
                    function()
                        qm:setSelfFill(
                            Options["Highlights_SelfFill"].Value,
                            Options["Highlights_SelfFill"].Transparency
                        )
                    end
                )
                Options["Highlights_SelfOutline"]:OnChanged(
                    function()
                        qm:setSelfOutline(
                            Options["Highlights_SelfOutline"].Value,
                            Options["Highlights_SelfOutline"].Transparency
                        )
                    end
                )
                Options["Highlights_OthersFill"]:OnChanged(
                    function()
                        qm:setOthersFill(
                            Options["Highlights_OthersFill"].Value,
                            Options["Highlights_OthersFill"].Transparency
                        )
                    end
                )
                Options["Highlights_OthersOutline"]:OnChanged(
                    function()
                        qm:setOthersOutline(
                            Options["Highlights_OthersOutline"].Value,
                            Options["Highlights_OthersOutline"].Transparency
                        )
                    end
                )
            end
        end
        do
            local qp = oI["Visuals"]:AddLeftGroupbox("Crosshair")
            do
                local qq = oz["Visuals_Crosshair"]
                if not qq then

                    return
                end
                local qr = qq(dL)
                local qs = qp:AddToggle("Crosshair_Enable", {Text = "Enable", Default = false})
                qs:AddColorPicker("Crosshair_Color1", {Default = Color3.fromRGB(255, 255, 255), Title = "Left"})
                qs:AddColorPicker("Crosshair_Color2", {Default = Color3.fromRGB(255, 255, 255), Title = "Right"})
                qs:AddColorPicker("Crosshair_Color3", {Default = Color3.fromRGB(255, 255, 255), Title = "Top"})
                qs:AddColorPicker("Crosshair_Color4", {Default = Color3.fromRGB(255, 255, 255), Title = "Bottom"})
                do
                    local qt = qp:AddDependencyBox()
                    qt:AddToggle("Crosshair_Chase", {Text = "Chase Cursor", Default = false})
                    qt:AddToggle("Crosshair_Rotate", {Text = "Rotate", Default = false})
                    qt:AddSlider(
                        "Crosshair_RotateSpeed",
                        {Text = "Rotate Speed", Default = 1, Min = 1, Max = 10, Rounding = 1}
                    )
                    qt:AddSlider(
                        "Crosshair_Thickness",
                        {Text = "Thickness", Default = 2, Min = 1, Max = 10, Rounding = 1}
                    )
                    qt:AddSlider("Crosshair_Length", {Text = "Length", Default = 10, Min = 1, Max = 100, Rounding = 1})
                    qt:AddSlider("Crosshair_Gap", {Text = "Gap", Default = 5, Min = 1, Max = 50, Rounding = 1})
                    qt:AddDivider()
                    local qu = qt:AddToggle("Crosshair_Indicator", {Text = "Indicator", Default = false})
                    qu:AddColorPicker(
                        "Crosshair_IndicatorColor1",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Color 1"}
                    )
                    qu:AddColorPicker(
                        "Crosshair_IndicatorColor2",
                        {Default = Color3.fromRGB(255, 255, 255), Title = "Color 2"}
                    )
                    qt:AddInput("Crosshair_IndicatorText", {Text = "Text", Default = "intellect"})
                    qt:SetupDependencies({{Toggles["Crosshair_Enable"], true}})
                end
                Toggles["Crosshair_Enable"]:OnChanged(
                    function()
                        qr:setEnable(Toggles["Crosshair_Enable"].Value)
                    end
                )
                Toggles["Crosshair_Chase"]:OnChanged(
                    function()
                        qr:setChase(Toggles["Crosshair_Chase"].Value)
                    end
                )
                Toggles["Crosshair_Rotate"]:OnChanged(
                    function()
                        qr:setRotate(Toggles["Crosshair_Rotate"].Value)
                    end
                )
                Options["Crosshair_RotateSpeed"]:OnChanged(
                    function()
                        qr:setRotateSpeed(Options["Crosshair_RotateSpeed"].Value)
                    end
                )
                Options["Crosshair_Thickness"]:OnChanged(
                    function()
                        qr:setThickness(Options["Crosshair_Thickness"].Value)
                    end
                )
                Options["Crosshair_Length"]:OnChanged(
                    function()
                        qr:setLength(Options["Crosshair_Length"].Value)
                    end
                )
                Options["Crosshair_Gap"]:OnChanged(
                    function()
                        qr:setGap(Options["Crosshair_Gap"].Value)
                    end
                )
                Toggles["Crosshair_Indicator"]:OnChanged(
                    function()
                        qr:setIndicator(Toggles["Crosshair_Indicator"].Value)
                    end
                )
                Options["Crosshair_IndicatorColor1"]:OnChanged(
                    function()
                        qr:setIndicatorColor1(Options["Crosshair_IndicatorColor1"].Value)
                    end
                )
                Options["Crosshair_IndicatorColor2"]:OnChanged(
                    function()
                        qr:setIndicatorColor2(Options["Crosshair_IndicatorColor2"].Value)
                    end
                )
                Options["Crosshair_IndicatorText"]:OnChanged(
                    function()
                        qr:setIndicatorText(Options["Crosshair_IndicatorText"].Value)
                    end
                )
                Options["Crosshair_Color1"]:OnChanged(
                    function()
                        qr:setColor1(Options["Crosshair_Color1"].Value)
                    end
                )
                Options["Crosshair_Color2"]:OnChanged(
                    function()
                        qr:setColor2(Options["Crosshair_Color2"].Value)
                    end
                )
                Options["Crosshair_Color3"]:OnChanged(
                    function()
                        qr:setColor3(Options["Crosshair_Color3"].Value)
                    end
                )
                Options["Crosshair_Color4"]:OnChanged(
                    function()
                        qr:setColor4(Options["Crosshair_Color4"].Value)
                    end
                )
            end
        end
        local qv = oI["Visuals"]:AddLeftGroupbox("ESP")
        qv:AddToggle("ESP_Enable", {Text = "Enable", Default = false})
        qv:AddToggle("ESP_Box", {Text = "Box", Default = false}):AddColorPicker(
            "ESP_Box_Color1",
            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 1"}
        ):AddColorPicker("ESP_Box_Color2", {Default = Color3.fromRGB(255, 255, 255), Title = "Color 2"}):AddColorPicker(
            "ESP_Box_Color3",
            {Default = Color3.fromRGB(255, 255, 255), Title = "Color 3"}
        ):AddColorPicker("ESP_Box_Color4", {Default = Color3.fromRGB(255, 255, 255), Title = "Color 4"})
        do
            local qw = qv:AddDependencyBox()
            qw:AddToggle("ESP_Box_Lerp", {Text = "Lerp", Default = false})
            local qx = qw:AddDependencyBox()
            qx:AddSlider(
                "ESP_Box_LerpSpeed",
                {Text = "Speed", Default = 0.3, Min = 0.1, Max = 2, Rounding = 1, Compact = false}
            )
            qx:SetupDependencies({{Toggles["ESP_Box_Lerp"], true}})
            qw:SetupDependencies({{Toggles["ESP_Box"], true}})
        end
        qv:AddToggle("ESP_Health", {Text = "Health", Default = false}):AddColorPicker(
            "ESP_Health_Color1",
            {Default = Color3.fromRGB(0, 255, 0), Title = "Color 1"}
        ):AddColorPicker("ESP_Health_Color2", {Default = Color3.fromRGB(0, 255, 0), Title = "Color 2"}):AddColorPicker(
            "ESP_Health_Color3",
            {Default = Color3.fromRGB(0, 255, 0), Title = "Color 3"}
        ):AddColorPicker("ESP_Health_Color4", {Default = Color3.fromRGB(0, 255, 0), Title = "Color 4"})
        do
            local qy = qv:AddDependencyBox()
            qy:AddToggle("ESP_Health_Lerp", {Text = "Lerp", Default = false})
            local qz = qy:AddDependencyBox()
            qz:AddSlider(
                "ESP_Health_LerpSpeed",
                {Text = "Speed", Default = 0.3, Min = 0.1, Max = 2, Rounding = 1, Compact = false}
            )
            qz:SetupDependencies({{Toggles["ESP_Health_Lerp"], true}})
            qy:SetupDependencies({{Toggles["ESP_Health"], true}})
        end
        qv:AddToggle("ESP_Armor", {Text = "Armor", Default = false}):AddColorPicker(
            "ESP_Armor_Color1",
            {Default = Color3.fromRGB(0, 150, 255), Title = "Color 1"}
        ):AddColorPicker("ESP_Armor_Color2", {Default = Color3.fromRGB(0, 150, 255), Title = "Color 2"}):AddColorPicker(
            "ESP_Armor_Color3",
            {Default = Color3.fromRGB(0, 150, 255), Title = "Color 3"}
        ):AddColorPicker("ESP_Armor_Color4", {Default = Color3.fromRGB(0, 150, 255), Title = "Color 4"})
        do
            local qA = qv:AddDependencyBox()
            qA:AddToggle("ESP_Armor_Lerp", {Text = "Lerp", Default = false})
            local qB = qA:AddDependencyBox()
            qB:AddSlider(
                "ESP_Armor_LerpSpeed",
                {Text = "Speed", Default = 0.3, Min = 0.1, Max = 2, Rounding = 1, Compact = false}
            )
            qB:SetupDependencies({{Toggles["ESP_Armor_Lerp"], true}})
            qA:SetupDependencies({{Toggles["ESP_Armor"], true}})
        end
        qv:AddDivider()
        qv:AddLabel("Text ESP")
        qv:AddToggle("ESP_Name", {Text = "Name", Default = false}):AddColorPicker(
            "ESP_Name_Color",
            {Default = Color3.fromRGB(255, 255, 255)}
        )
        do
            local qC = qv:AddDependencyBox()
            qC:AddDropdown(
                "ESP_Name_Font",
                {
                    Text = "Font",
                    Default = 1,
                    Values = {
                        "Arial",
                        "ArialBold",
                        "Bodoni",
                        "BuilderSans",
                        "BuilderSansBold",
                        "Code",
                        "Creepster",
                        "DenkOne",
                        "Fantasy",
                        "Fondamento",
                        "Gotham",
                        "GothamBlack",
                        "GothamBold",
                        "GothamMedium",
                        "Grenze",
                        "GrenzeGotisch",
                        "Highway",
                        "Jura",
                        "JuraBold",
                        "Legacy",
                        "Merriweather",
                        "Michroma",
                        "Nunito",
                        "Oswald",
                        "PatrickHand",
                        "PermanentMarker",
                        "Roboto",
                        "RobotoBold",
                        "RobotoCondensed",
                        "RobotoMono",
                        "SourceSans",
                        "SourceSansBold",
                        "SourceSansItalic",
                        "SourceSansLight",
                        "SourceSansSemibold",
                        "Sarpanch",
                        "SciFi",
                        "SpecialElite",
                        "TitilliumWeb",
                        "Ubuntu"
                    }
                }
            )
            qC:AddSlider(
                "ESP_Name_Size",
                {Text = "Text Size", Default = 11, Min = 9, Max = 14, Rounding = 0, Compact = false}
            )
            qC:SetupDependencies({{Toggles["ESP_Name"], true}})
        end
        qv:AddToggle("ESP_Distance", {Text = "Distance", Default = false}):AddColorPicker(
            "ESP_Distance_Color",
            {Default = Color3.fromRGB(255, 255, 255)}
        )
        do
            local qD = qv:AddDependencyBox()
            qD:AddDropdown(
                "ESP_Distance_Font",
                {
                    Text = "Font",
                    Default = 1,
                    Values = {
                        "Arial",
                        "ArialBold",
                        "Bodoni",
                        "BuilderSans",
                        "BuilderSansBold",
                        "Code",
                        "Creepster",
                        "DenkOne",
                        "Fantasy",
                        "Fondamento",
                        "Gotham",
                        "GothamBlack",
                        "GothamBold",
                        "GothamMedium",
                        "Grenze",
                        "GrenzeGotisch",
                        "Highway",
                        "Jura",
                        "JuraBold",
                        "Legacy",
                        "Merriweather",
                        "Michroma",
                        "Nunito",
                        "Oswald",
                        "PatrickHand",
                        "PermanentMarker",
                        "Roboto",
                        "RobotoBold",
                        "RobotoCondensed",
                        "RobotoMono",
                        "SourceSans",
                        "SourceSansBold",
                        "SourceSansItalic",
                        "SourceSansLight",
                        "SourceSansSemibold",
                        "Sarpanch",
                        "SciFi",
                        "SpecialElite",
                        "TitilliumWeb",
                        "Ubuntu"
                    }
                }
            )
            qD:AddSlider(
                "ESP_Distance_Size",
                {Text = "Text Size", Default = 11, Min = 9, Max = 14, Rounding = 0, Compact = false}
            )
            qD:SetupDependencies({{Toggles["ESP_Distance"], true}})
        end
        qv:AddToggle("ESP_Tool", {Text = "Tool", Default = false}):AddColorPicker(
            "ESP_Tool_Color",
            {Default = Color3.fromRGB(255, 255, 255)}
        )
        do
            local qE = qv:AddDependencyBox()
            qE:AddDropdown(
                "ESP_Tool_Font",
                {
                    Text = "Font",
                    Default = 1,
                    Values = {
                        "Arial",
                        "ArialBold",
                        "Bodoni",
                        "BuilderSans",
                        "BuilderSansBold",
                        "Code",
                        "Creepster",
                        "DenkOne",
                        "Fantasy",
                        "Fondamento",
                        "Gotham",
                        "GothamBlack",
                        "GothamBold",
                        "GothamMedium",
                        "Grenze",
                        "GrenzeGotisch",
                        "Highway",
                        "Jura",
                        "JuraBold",
                        "Legacy",
                        "Merriweather",
                        "Michroma",
                        "Nunito",
                        "Oswald",
                        "PatrickHand",
                        "PermanentMarker",
                        "Roboto",
                        "RobotoBold",
                        "RobotoCondensed",
                        "RobotoMono",
                        "SourceSans",
                        "SourceSansBold",
                        "SourceSansItalic",
                        "SourceSansLight",
                        "SourceSansSemibold",
                        "Sarpanch",
                        "SciFi",
                        "SpecialElite",
                        "TitilliumWeb",
                        "Ubuntu"
                    }
                }
            )
            qE:AddSlider(
                "ESP_Tool_Size",
                {Text = "Text Size", Default = 11, Min = 9, Max = 14, Rounding = 0, Compact = false}
            )
            qE:SetupDependencies({{Toggles["ESP_Tool"], true}})
        end
        do
            local qF = oz["Visuals_ESP"]
            if ((1090 <= 4827) and not qF) then

                return
            end
            local qG = qF(dL)
            local qH
            Toggles["ESP_Enable"]:OnChanged(
                function()
                    if Toggles["ESP_Enable"]["Value"] then
                        if (qH or (239 > 1345)) then
                            qH:Disconnect()
                            qH = nil
                        end
                        if kF["connections"]["espPlayerAdded"] then
                            kF["connections"]["espPlayerAdded"]:Disconnect()
                            kF["connections"]["espPlayerAdded"] = nil
                        end
                        if kF["connections"]["espPlayerRemoving"] then
                            kF["connections"]["espPlayerRemoving"]:Disconnect()
                            kF["connections"]["espPlayerRemoving"] = nil
                        end
                        for d_, k1 in pairs(kF.connections) do
                            if (d_:match("^CharacterAdded_") or (3710 >= 3738)) then
                                k1:Disconnect()
                                kF["connections"][d_] = nil
                            end
                        end
                        qG:clearAll()
                        for D, eV in pairs(dL["players"]:GetPlayers()) do
                            if ((eV ~= dL["lp"]) or (3838 < 2061)) then
                                if (eV["Character"] or (690 > 1172)) then
                                    local l9 = qG:createBox(eV)
                                    if (l9 or (1592 > 2599)) then
                                        qG:setESP(eV, l9)
                                    end
                                end
                                local lJ = "CharacterAdded_" .. eV["Name"]
                                if kF["connections"][lJ] then
                                    kF["connections"][lJ]:Disconnect()
                                end
                                kF["connections"][lJ] =
                                    eV["CharacterAdded"]:Connect(
                                    function(dS)
                                        task.wait(0.1)
                                        qG:removeBox(eV)
                                        local l9 = qG:createBox(eV)
                                        if ((3574 <= 4397) and l9) then
                                            qG:setESP(eV, l9)
                                        end
                                    end
                                )
                            end
                        end
                        qH =
                            dL["rnd"]:Connect(
                            function()
                                if ((3135 > 1330) and not Toggles["ESP_Enable"]["Value"]) then
                                    return
                                end
                                local lb = {
                                    boxEnable = Toggles["ESP_Box"]["Value"],
                                    boxLerp = ((Toggles["ESP_Box_Lerp"] and Toggles["ESP_Box_Lerp"]["Value"]) or false),
                                    boxLerpSpeed = ((Options["ESP_Box_LerpSpeed"] and
                                        Options["ESP_Box_LerpSpeed"]["Value"]) or
                                        0.3),
                                    boxColors = {
                                        Options["ESP_Box_Color1"]["Value"],
                                        Options["ESP_Box_Color2"]["Value"],
                                        Options["ESP_Box_Color3"]["Value"],
                                        Options["ESP_Box_Color4"]["Value"]
                                    },
                                    healthEnable = Toggles["ESP_Health"]["Value"],
                                    healthLerp = ((Toggles["ESP_Health_Lerp"] and Toggles["ESP_Health_Lerp"]["Value"]) or
                                        false),
                                    healthLerpSpeed = ((Options["ESP_Health_LerpSpeed"] and
                                        Options["ESP_Health_LerpSpeed"]["Value"]) or
                                        0.3),
                                    healthColors = {
                                        Options["ESP_Health_Color1"]["Value"],
                                        Options["ESP_Health_Color2"]["Value"],
                                        Options["ESP_Health_Color3"]["Value"],
                                        Options["ESP_Health_Color4"]["Value"]
                                    },
                                    armorEnable = Toggles["ESP_Armor"]["Value"],
                                    armorLerp = ((Toggles["ESP_Armor_Lerp"] and Toggles["ESP_Armor_Lerp"]["Value"]) or
                                        false),
                                    armorLerpSpeed = ((Options["ESP_Armor_LerpSpeed"] and
                                        Options["ESP_Armor_LerpSpeed"]["Value"]) or
                                        0.3),
                                    armorColors = {
                                        Options["ESP_Armor_Color1"]["Value"],
                                        Options["ESP_Armor_Color2"]["Value"],
                                        Options["ESP_Armor_Color3"]["Value"],
                                        Options["ESP_Armor_Color4"]["Value"]
                                    },
                                    nameEnable = ((Toggles["ESP_Name"] and Toggles["ESP_Name"]["Value"]) or false),
                                    nameColor = ((Options["ESP_Name_Color"] and Options["ESP_Name_Color"]["Value"]) or
                                        Color3.fromRGB(255, 255, 255)),
                                    nameFont = ((Options["ESP_Name_Font"] and Options["ESP_Name_Font"]["Value"]) or
                                        "Arial"),
                                    nameSize = ((Options["ESP_Name_Size"] and Options["ESP_Name_Size"]["Value"]) or 11),
                                    distanceEnable = ((Toggles["ESP_Distance"] and Toggles["ESP_Distance"]["Value"]) or
                                        false),
                                    distanceColor = ((Options["ESP_Distance_Color"] and
                                        Options["ESP_Distance_Color"]["Value"]) or
                                        Color3.fromRGB(255, 255, 255)),
                                    distanceFont = ((Options["ESP_Distance_Font"] and
                                        Options["ESP_Distance_Font"]["Value"]) or
                                        "Arial"),
                                    distanceSize = ((Options["ESP_Distance_Size"] and
                                        Options["ESP_Distance_Size"]["Value"]) or
                                        11),
                                    toolEnable = ((Toggles["ESP_Tool"] and Toggles["ESP_Tool"]["Value"]) or false),
                                    toolColor = ((Options["ESP_Tool_Color"] and Options["ESP_Tool_Color"]["Value"]) or
                                        Color3.fromRGB(255, 255, 255)),
                                    toolFont = ((Options["ESP_Tool_Font"] and Options["ESP_Tool_Font"]["Value"]) or
                                        "Arial"),
                                    toolSize = ((Options["ESP_Tool_Size"] and Options["ESP_Tool_Size"]["Value"]) or 11)
                                }
                                qG:updateAllBoxes(lb)
                            end
                        )
                        kF["connections"]["espPlayerAdded"] =
                            dL["players"]["PlayerAdded"]:Connect(
                            function(eV)
                                if ((eV ~= dL["lp"]) or (3900 <= 3641)) then
                                    if ((1724 == 1724) and not eV["Character"]) then
                                        eV["CharacterAdded"]:Wait()
                                    end
                                    task.wait(0.1)
                                    local l9 = qG:createBox(eV)
                                    if ((455 <= 1282) and l9) then
                                        qG:setESP(eV, l9)
                                    end
                                    local lJ = "CharacterAdded_" .. eV["Name"]
                                    if ((4606 < 4876) and kF["connections"][lJ]) then
                                        kF["connections"][lJ]:Disconnect()
                                    end
                                    kF["connections"][lJ] =
                                        eV["CharacterAdded"]:Connect(
                                        function(dS)
                                            task.wait(0.1)
                                            qG:removeBox(eV)
                                            local l9 = qG:createBox(eV)
                                            if l9 then
                                                qG:setESP(eV, l9)
                                            end
                                        end
                                    )
                                end
                            end
                        )
                        kF["connections"]["espPlayerRemoving"] =
                            dL["players"]["PlayerRemoving"]:Connect(
                            function(eV)
                                qG:removeBox(eV)
                                local lJ = "CharacterAdded_" .. eV["Name"]
                                if (kF["connections"][lJ] or (1442 > 2640)) then
                                    kF["connections"][lJ]:Disconnect()
                                    kF["connections"][lJ] = nil
                                end
                            end
                        )
                    else
                        if ((136 < 3668) and qH) then
                            qH:Disconnect()
                            qH = nil
                        end
                        if (kF["connections"]["espPlayerAdded"] or (1784 > 4781)) then
                            kF["connections"]["espPlayerAdded"]:Disconnect()
                            kF["connections"]["espPlayerAdded"] = nil
                        end
                        if kF["connections"]["espPlayerRemoving"] then
                            kF["connections"]["espPlayerRemoving"]:Disconnect()
                            kF["connections"]["espPlayerRemoving"] = nil
                        end
                        for d_, k1 in pairs(kF.connections) do
                            if ((4585 > 3298) and d_:match("^CharacterAdded_")) then
                                k1:Disconnect()
                                kF["connections"][d_] = nil
                            end
                        end
                        qG:clearAll()
                    end
                end
            )
        end
    end
    do

        local qI = oI["Visuals"]:AddRightGroupbox("HitDetect")
        qI:AddToggle("HitDetect_Enable", {Text = "Enable", Default = false})
        qI:AddToggle("HitDetect_Notify", {Text = "Notify", Default = false})
        do
            local qJ = qI:AddDependencyBox()
            qJ:AddDropdown(
                "HitDetect_NotifyInfo",
                {
                    Text = "Notify Info",
                    Multi = true,
                    Default = 1,
                    Values = {"Nickname", "DisplayName", "HitPart", "LastHP", "Distance"}
                }
            )
            qJ:SetupDependencies({{Toggles["HitDetect_Notify"], true}})
        end
        local qK = qI:AddToggle("HitDetect_Chams", {Text = "Chams", Default = false})
        qK:AddColorPicker(
            "HitDetect_ChamsColor",
            {Default = Color3.fromRGB(255, 0, 0), Title = "Chams Color", Transparency = 0}
        )
        do
            local qL = qI:AddDependencyBox()
            qL:AddDropdown(
                "HitDetect_ChamsMaterial",
                {Text = "Material", Default = 1, Values = {"Neon", "ForceField", "Glass"}}
            )
            qL:AddSlider("HitDetect_ChamsLifetime", {Text = "Lifetime", Min = 0.5, Max = 10, Default = 2, Rounding = 1})
            qL:SetupDependencies({{Toggles["HitDetect_Chams"], true}})
        end
        do
            local qM = oz["Visuals_HitDetect"]
            if (not qM or (1664 > 1698)) then

                return
            end
            local qN = qM(dL)
            qN:init(nP)
            qI:AddToggle("HitDetect_Sound", {Text = "Sound", Default = false})
            do
                local qO = qI:AddDependencyBox()
                local qP = qN:getSounds()
                local qQ =
                    qO:AddDropdown(
                    "HitDetect_SoundName",
                    {Text = "Sound", Default = 1, Values = ((qP and (#qP > 0) and qP) or {"skeet"})}
                )
                qO:AddSlider("HitDetect_SoundVolume", {Text = "Volume", Min = 0, Max = 10, Default = 0.5, Rounding = 1})
                qO:AddSlider("HitDetect_SoundPitch", {Text = "Pitch", Min = 0, Max = 3, Default = 1, Rounding = 2})
                qO:SetupDependencies({{Toggles["HitDetect_Sound"], true}})
                task.spawn(
                    function()
                        task.wait(1)
                        local mO = qN:getSounds()
                        if ((mO and (#mO > 0) and (#mO > #qP)) or (3427 < 2849)) then
                            qQ:SetValues(mO)
                        end
                    end
                )
            end
            local qR = qI:AddToggle("HitDetect_Effects", {Text = "Effects", Default = false})
            qR:AddColorPicker(
                "HitDetect_EffectsColor",
                {Default = Color3.fromRGB(255, 255, 255), Title = "Effects Color"}
            )
            do
                local qS = qI:AddDependencyBox()
                qS:AddDropdown(
                    "HitDetect_EffectsType",
                    {Text = "Type", Default = 1, Values = {"Dots", "Portal", "Fortnite", "Explode"}}
                )
                qS:SetupDependencies({{Toggles["HitDetect_Effects"], true}})
            end
            Toggles["HitDetect_Enable"]:OnChanged(
                function()
                    qN:setEnable(Toggles["HitDetect_Enable"].Value)
                end
            )
            Toggles["HitDetect_Notify"]:OnChanged(
                function()
                    qN:setNotify(Toggles["HitDetect_Notify"].Value)
                end
            )
            Options["HitDetect_NotifyInfo"]:OnChanged(
                function()
                    qN:setNotifyOptions(Options["HitDetect_NotifyInfo"].Value)
                end
            )
            Toggles["HitDetect_Chams"]:OnChanged(
                function()
                    qN:setChams(Toggles["HitDetect_Chams"].Value)
                end
            )
            Options["HitDetect_ChamsColor"]:OnChanged(
                function()
                    qN:setChamsColor(
                        Options["HitDetect_ChamsColor"].Value,
                        Options["HitDetect_ChamsColor"].Transparency
                    )
                end
            )
            Options["HitDetect_ChamsMaterial"]:OnChanged(
                function()
                    qN:setChamsMaterial(Options["HitDetect_ChamsMaterial"].Value)
                end
            )
            Options["HitDetect_ChamsLifetime"]:OnChanged(
                function()
                    qN:setChamsLifetime(Options["HitDetect_ChamsLifetime"].Value)
                end
            )
            Toggles["HitDetect_Sound"]:OnChanged(
                function()
                    qN:setSound(Toggles["HitDetect_Sound"].Value)
                end
            )
            Options["HitDetect_SoundName"]:OnChanged(
                function()
                    qN:setSoundName(Options["HitDetect_SoundName"].Value)
                end
            )
            Options["HitDetect_SoundVolume"]:OnChanged(
                function()
                    qN:setSoundVolume(Options["HitDetect_SoundVolume"].Value)
                end
            )
            Options["HitDetect_SoundPitch"]:OnChanged(
                function()
                    qN:setSoundPitch(Options["HitDetect_SoundPitch"].Value)
                end
            )
            Toggles["HitDetect_Effects"]:OnChanged(
                function()
                    qN:setEffects(Toggles["HitDetect_Effects"].Value)
                end
            )
            Options["HitDetect_EffectsColor"]:OnChanged(
                function()
                    qN:setEffectsColor(Options["HitDetect_EffectsColor"].Value)
                end
            )
            Options["HitDetect_EffectsType"]:OnChanged(
                function()
                    qN:setEffectsType(Options["HitDetect_EffectsType"].Value)
                end
            )
        end
    end
    do
        local qT = oI["Visuals"]:AddRightGroupbox("Auras")
        do
            local qU = oz["Visuals_Auras"]
            if not qU then

                return
            end
            local qV = qU(dL)
            qV:init()
            local qW = qT:AddToggle("Auras_Enable", {Text = "Enable", Default = false})
            qW:AddColorPicker("Auras_Color", {Default = Color3.fromRGB(133, 220, 255), Title = "Aura Color"})
            do
                local qX = qT:AddDependencyBox()
                qX:AddDropdown(
                    "Auras_Types",
                    {Text = "Types", Multi = true, AllowNull = true, Values = {"Angelic", "Ambient", "Nimb", "Tornado"}}
                )
                qX:SetupDependencies({{Toggles["Auras_Enable"], true}})
            end
            Toggles["Auras_Enable"]:OnChanged(
                function()
                    qV:setEnable(Toggles["Auras_Enable"].Value)
                end
            )
            Options["Auras_Color"]:OnChanged(
                function()
                    qV:setAuraColor(Options["Auras_Color"].Value)
                end
            )
            Options["Auras_Types"]:OnChanged(
                function()
                    qV:setAuraTypes(Options["Auras_Types"].Value)
                end
            )
        end
    end
    do
        local qY = oI["Visuals"]:AddRightGroupbox("Bullet Tracers")
        do
            local qZ = oz["Visuals_BulletTracers"]
            if not qZ then

                return
            end
            local q_ = qZ(dL)
            q_:init(dL.hooks)
            local r0 = qY:AddToggle("BulletTracers_Enable", {Text = "Enable", Default = false})
            r0:AddColorPicker(
                "BulletTracers_Color",
                {Default = Color3.fromRGB(155, 125, 175), Title = "Tracer Color", Transparency = 0}
            )
            do
                local r1 = qY:AddDependencyBox()
                r1:AddDropdown("BulletTracers_Mode", {Text = "Mode", Default = 1, Values = {"Beam", "Drawing"}})
                r1:AddDropdown(
                    "BulletTracers_Texture",
                    {
                        Text = "Texture",
                        Default = 2,
                        Values = {"Beam", "Lightning", "Heartrate", "Chain", "Glitch", "Swirl"}
                    }
                )
                r1:AddSlider("BulletTracers_Size", {Text = "Size", Min = 0.1, Max = 3, Default = 1, Rounding = 2})
                r1:AddSlider(
                    "BulletTracers_Lifetime",
                    {Text = "Lifetime", Min = 0.5, Max = 10, Default = 3, Rounding = 1, Suffix = "s"}
                )
                r1:SetupDependencies({{Toggles["BulletTracers_Enable"], true}})
            end
            Toggles["BulletTracers_Enable"]:OnChanged(
                function()
                    q_:setEnable(Toggles["BulletTracers_Enable"].Value)
                end
            )
            Options["BulletTracers_Color"]:OnChanged(
                function()
                    q_:setColor(Options["BulletTracers_Color"].Value, Options["BulletTracers_Color"].Transparency)
                end
            )
            Options["BulletTracers_Mode"]:OnChanged(
                function()
                    q_:setMode(Options["BulletTracers_Mode"].Value)
                end
            )
            Options["BulletTracers_Texture"]:OnChanged(
                function()
                    local r2 = {
                        Beam = "rbxassetid://12781852245",
                        Lightning = "rbxassetid://446111271",
                        Heartrate = "rbxassetid://5830549480",
                        Chain = "rbxassetid://9632168658",
                        Glitch = "rbxassetid://8089467613",
                        Swirl = "rbxassetid://5638168605"
                    }
                    q_:setTexture(r2[Options["BulletTracers_Texture"]["Value"]] or r2["Lightning"])
                end
            )
            Options["BulletTracers_Size"]:OnChanged(
                function()
                    q_:setSize(Options["BulletTracers_Size"].Value)
                end
            )
            Options["BulletTracers_Lifetime"]:OnChanged(
                function()
                    q_:setLifetime(Options["BulletTracers_Lifetime"].Value)
                end
            )
        end
    end
    do
        local r3 = oI["Visuals"]:AddRightGroupbox("Textures")
        do
            local r4 = oz["Visuals_Textures"]
            if not r4 then

                return
            end
            local r5 = r4(dL)
            r5:init()
            local r6 = r3:AddToggle("Textures_Enable", {Text = "Enable", Default = false})
            do
                local r7 = r3:AddDependencyBox()
                r7:AddDropdown("Textures_Type", {Text = "Type", Default = 1, Values = {"Minecraft"}})
                r7:SetupDependencies({{Toggles["Textures_Enable"], true}})
            end
            Toggles["Textures_Enable"]:OnChanged(
                function()
                    r5:setEnable(Toggles["Textures_Enable"].Value)
                end
            )
            Options["Textures_Type"]:OnChanged(
                function()
                    r5:setType(Options["Textures_Type"].Value)
                end
            )
        end
    end
    do
        local r8 = oI["Visuals"]:AddRightGroupbox("Weather")
        do
            local r9 = oz["Visuals_Weather"]
            if ((3616 <= 4429) and not r9) then

                return
            end
            local ra = r9(dL)
            ra:init()
            local rb = r8:AddToggle("Weather_Enable", {Text = "Enable", Default = false})
            rb:AddColorPicker("Weather_Color", {Default = Color3.fromRGB(255, 255, 255), Title = "Emitter Color"})
            do
                local rc = r8:AddDependencyBox()
                rc:AddDropdown("Weather_Type", {Text = "Type", Default = 1, Values = {"Rain", "Snow", "Autumn"}})
                rc:SetupDependencies({{Toggles["Weather_Enable"], true}})
            end
            Toggles["Weather_Enable"]:OnChanged(
                function()
                    ra:setEnable(Toggles["Weather_Enable"].Value)
                end
            )
            Options["Weather_Color"]:OnChanged(
                function()
                    ra:setColor(Options["Weather_Color"].Value)
                end
            )
            Options["Weather_Type"]:OnChanged(
                function()
                    ra:setType(Options["Weather_Type"].Value)
                end
            )
        end
    end




    do
        local rd = oz["HUD"]
        if rd then
            local re = oI["Settings"]:AddLeftGroupbox("HUD")
            rd(re, nP, dL)
        end
        if ((3988 >= 66) and oE) then
            oE:setLibrary(nP)
            oE:setFolder("intellect")
            local rf = oI["Settings"]:AddLeftGroupbox("Theme Manager")
            oE:applyToGroupbox(rf)
        end
        if (oF or (862 > 4644)) then 
            oF:setLibrary(nP)
            oF:setFolder("intellect") 
            oF:ignoreTheme()
            local rg = oI["Settings"]:AddRightGroupbox("Config Manager")
            oF:buildSection(rg)
            oF:autoload()
        end
        if oG then
            local rh = oI["Settings"]:AddRightGroupbox("Server Utils")
            oG:buildSection(rh, nP, dL)
        end
    end
end


Library:Notify(
    "Welcome back, @" .. game.Players.LocalPlayer.Name,
    5
)

