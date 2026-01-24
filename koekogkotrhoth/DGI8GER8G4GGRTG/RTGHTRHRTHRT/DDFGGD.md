-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local LHBR1 = Instance.new("ImageLabel")
local TextLabel = Instance.new("TextLabel")
local Text = Instance.new("TextLabel")
local UICorner = Instance.new("UICorner")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

LHBR1.Name = "LHBR1"
LHBR1.Parent = ScreenGui
LHBR1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
LHBR1.BackgroundTransparency = 1.000
LHBR1.BorderColor3 = Color3.fromRGB(0, 0, 0)
LHBR1.BorderSizePixel = 0
LHBR1.Position = UDim2.new(0.770883858, 0, 0.71718365, 0)
LHBR1.Size = UDim2.new(0.221704021, 0, 0.261273623, 0)
LHBR1.ZIndex = 0
LHBR1.Image = "rbxassetid://94897440560038"

TextLabel.Parent = LHBR1
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0.272058815, 0, 0.0890053436, 0)
TextLabel.Size = UDim2.new(0.198529407, 0, 0.189189196, 0)
TextLabel.Font = Enum.Font.SourceSansBold
TextLabel.Text = "We found nothing related to this topic."
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextStrokeTransparency = 0.000
TextLabel.TextWrapped = true

Text.Name = "Text"
Text.Parent = LHBR1
Text.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Text.BackgroundTransparency = 1.000
Text.BorderColor3 = Color3.fromRGB(0, 0, 0)
Text.BorderSizePixel = 0
Text.Position = UDim2.new(0.128676474, 0, 0.567567587, 0)
Text.Size = UDim2.new(0.827205896, 0, 0.391891897, 0)
Text.Font = Enum.Font.Unknown
Text.Text = "..."
Text.TextColor3 = Color3.fromRGB(255, 255, 255)
Text.TextScaled = true
Text.TextSize = 14.000
Text.TextWrapped = true
Text.TextXAlignment = Enum.TextXAlignment.Left
Text.TextYAlignment = Enum.TextYAlignment.Top

UICorner.CornerRadius = UDim.new(0, 19)
UICorner.Parent = LHBR1

-- Scripts:

local function OSGP_fake_script() -- Text.Traduction 
	local script = Instance.new('LocalScript', Text)

	local textLabel = script.Parent 
	local LocalizationService = game:GetService("LocalizationService") -- Service pour la localisation
	
	-- Détection de la langue du joueur (on prend les 2 premières lettres)
	-- Ex: "fr-fr" devient "fr"
	local langue = LocalizationService.RobloxLocaleId:lower() 
	
	-- Ton dictionnaire avec TES traductions exactes
	local dictionnaireMKN = {
		["fr"] = "⚠️ Je suis désolé de vous annoncer que ce mot de passe n'est plus disponible ou est obsolète. ❌ Il est possible que le code soit mauvais ou qu'il manque un caractère. Veuillez recommencer la tâche pour revoir le mot de passe. 🔄",
	
		["en"] = "⚠️ I am sorry to announce that this password is no longer available or is obsolete. ❌ It is possible that the code is wrong or missing a character. Please restart the task to review the password. 🔄",
	
		["es"] = "⚠️ Siento comunicarle que esta contraseña ya no está disponible o está obsoleta. ❌ Es posible que el código sea incorrecto o que falte un carácter. Por favor, reinicie la tarea para revisar la contraseña. 🔄",
	
		["ja"] = "「このような状況にある場合は、ゲームが間違っていて別のゲームにいるか、または当社のディレクトリに既に存在しない可能性があるため、当社のサービスにご連絡ください。」",
	
		["pt"] = "⚠️ Lamento informar que esta senha não está mais disponível ou está obsoleta. ❌ É possível que o código esteja errado ou faltando um caractere. Por favor, reinicie a tarefa para rever a senha. 🔄"
	}
	
	local function appliquerTraduction() -- Fonction pour appliquer la traduction
		-- On vérifie chaque langue spécifique
		if langue:sub(1,2) == "fr" then-- Français
			textLabel.Text = dictionnaireMKN["fr"] -- Français
		elseif langue:sub(1,2) == "en" then-- Anglais
			textLabel.Text = dictionnaireMKN["en"] -- Anglais
		elseif langue:sub(1,2) == "es" then-- Espagnol
			textLabel.Text = dictionnaireMKN["es"] -- Espagnol
		elseif langue:sub(1,2) == "ja" then-- Japonais
			textLabel.Text = dictionnaireMKN["ja"] -- Japonais
		elseif langue:sub(1,2) == "pt" then-- Portugais
			textLabel.Text = dictionnaireMKN["pt"] -- Portugais
		else
			-- Si la langue est inconnue, on met l'Anglais par défaut
			textLabel.Text = dictionnaireMKN["en"] -- Anglais par défaut
		end
	end
	
	-- Exécution au démarrage
	appliquerTraduction()
	
	
	
end
coroutine.wrap(OSGP_fake_script)()
local function REKZXXN_fake_script() -- LHBR1.LocalScript 
	local script = Instance.new('LocalScript', LHBR1)

	local TweenService = game:GetService("TweenService")
	
	local image = script.Parent -- Ton ImageLabel / ImageButton
	local gui = image:FindFirstAncestorOfClass("ScreenGui")
	
	-- Position normale
	local originalPosition = image.Position
	
	-- Position bas droite (hors écran)
	local offscreenPosition = UDim2.new(1, 0, 1, 0)
	
	-- Tween settings
	local tweenInInfo = TweenInfo.new(2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
	local tweenOutInfo = TweenInfo.new(2, Enum.EasingStyle.Quad, Enum.EasingDirection.In)
	
	-- Départ invisible en bas droite
	image.Position = offscreenPosition
	image.ImageTransparency = 1
	
	-- Animation entrée
	local tweenIn = TweenService:Create(image, tweenInInfo, {
		Position = originalPosition,
		ImageTransparency = 0
	})
	
	-- Animation sortie
	local tweenOut = TweenService:Create(image, tweenOutInfo, {
		Position = offscreenPosition,
		ImageTransparency = 1
	})
	
	-- Lancer entrée
	tweenIn:Play()
	tweenIn.Completed:Wait()
	
	-- Rester 10 secondes
	task.wait(7)
	
	-- Sortir
	tweenOut:Play()
	tweenOut.Completed:Wait()
	
	-- SUPPRIMER LE GUI COMPLET
	if gui then
		gui:Destroy()
	end
	
end
coroutine.wrap(REKZXXN_fake_script)()
