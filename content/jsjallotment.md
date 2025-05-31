---
created: 2025-05-31T20:57
updated: 2025-05-31T21:14
draft: false
title: JSJallotment
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JSJ allotment - Digital Pick-Your-Own for Growing Healthy Churches</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            font-family: 'Georgia', serif;
            background: linear-gradient(135deg, #e8f5e8 0%, #d4edda 100%);
            min-height: 100vh;
        }
        
        .garden-container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .garden-title {
            text-align: center;
            color: #2d5016;
            font-size: 2.1em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        
        .garden-subtitle {
            text-align: center;
            color: #5a6c57;
            font-size: 1.2em;
            margin-bottom: 30px;
            font-style: italic;
        }
        
        .user-journey {
            margin-bottom: 30px;
            background: linear-gradient(135deg, #e3f2fd 0%, #90caf9 100%);
            padding: 20px;
            border-radius: 10px;
            border: 2px solid #1976d2;
        }
        
        .journey-title {
            font-size: 1.2em;
            font-weight: bold;
            color: #0d47a1;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .journey-steps {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .journey-step {
            background: rgba(255, 255, 255, 0.9);
            padding: 10px;
            border-radius: 8px;
            text-align: left;
            font-size: 0.8em;
            color: #1565c0;
            min-width: 120px;
            border: 1px solid #42a5f5;
        }
        
        .step-number {
            font-weight: bold;
            color: #0d47a1;
        }
        
        .legend {
            margin-bottom: 30px;
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            border: 2px solid #8B4513;
        }
        
        .legend-title {
            font-size: 1.2em;
            font-weight: bold;
            color: #2d5016;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .legend-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 15px;
        }
        
        .legend-item {
            display: flex;
            align-items: flex-start;
            font-size: 0.9em;
            padding: 8px;
            background: rgba(248, 248, 248, 0.5);
            border-radius: 6px;
            box-sizing: border-box;
        }
        
        .legend-icon {
            font-size: 1.2em;
            margin-right: 10px;
            width: 25px;
            flex-shrink: 0;
            text-align: center;
        }
        
        .legend-text {
            flex: 1;
            word-wrap: break-word;
            overflow: hidden;
        }
        
        .circular-garden {
            position: relative;
            width: 800px;
            height: 800px;
            margin: 120px auto;
            border-radius: 50%;
            border: 4px solid #8B4513;
            background: radial-gradient(circle, #f8f8f8 30%, #e8f5e8 100%);
        }
        
        .central-hub {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 180px;
            height: 180px;
            background: linear-gradient(135deg, #fff3e0 0%, #ffb74d 100%);
            border: 4px solid #e65100;
            border-radius: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            z-index: 10;
            box-sizing: border-box;
            padding: 15px;
        }
        
        .hub-title {
            font-size: 1.1em;
            font-weight: bold;
            color: #e65100;
            margin-bottom: 8px;
            line-height: 1.2;
            word-wrap: break-word;
            overflow: hidden;
        }
        
        .hub-subtitle {
            font-size: 0.75em;
            color: #bf360c;
            text-align: center;
            line-height: 1.2;
            word-wrap: break-word;
            overflow: hidden;
        }
        
        .prayer-circle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 160px;
            height: 160px;
            border: 3px dashed #e65100;
            border-radius: 50%;
            animation: rotate 20s linear infinite;
        }
        
        @keyframes rotate {
            from { transform: translate(-50%, -50%) rotate(0deg); }
            to { transform: translate(-50%, -50%) rotate(360deg); }
        }
        
        .growing-bed {
            position: absolute;
            width: 280px;
            height: 180px;
            border: 3px solid #8B4513;
            border-radius: 15px;
            padding: 20px;
            transition: all 0.3s ease;
            cursor: pointer;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            box-sizing: border-box;
            overflow: hidden;
        }
        
        .growing-bed:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
            z-index: 5;
        }
        
        .bed-divine {
            background: linear-gradient(135deg, #fff9c4 0%, #f4e04d 100%);
            top: -80px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .bed-internal {
            background: linear-gradient(135deg, #e1f5fe 0%, #81d4fa 100%);
            top: 140px;
            left: -130px;
        }
        
        .bed-external {
            background: linear-gradient(135deg, #e8eaf6 0%, #9fa8da 100%);
            top: 500px;
            left: -140px;
        }
        
        .bed-creation {
            background: linear-gradient(135deg, #e8f5e8 0%, #66bb6a 100%);
            top: 140px;
            right: -130px;
        }
        
        .bed-time {
            background: linear-gradient(135deg, #f3e5f5 0%, #ba68c8 100%);
            bottom: -80px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .bed-title {
            font-size: 1.1em;
            font-weight: bold;
            color: #2d5016;
            margin-bottom: 8px;
            line-height: 1.2;
            text-decoration: none;
            cursor: pointer;
            transition: color 0.3s ease;
        }
        
        .bed-title:hover {
            color: #1a2f0c;
            text-decoration: underline;
        }
        
        .bed-subtitle {
            font-size: 0.8em;
            color: #5a6c57;
            margin-bottom: 15px;
            font-style: italic;
            line-height: 1.2;
        }
        
        .growth-indicators {
            display: flex;
            justify-content: space-between;
            width: 100%;
            gap: 5px;
            flex-wrap: nowrap;
            align-items: flex-start;
        }
        
        .growth-stage {
            display: flex;
            flex-direction: column;
            align-items: center;
            font-size: 0.75em;
            text-align: center;
            flex: 1;
            min-width: 0;
            max-width: 25%;
        }
        
        .stage-icon {
            font-size: 1.4em;
            margin-bottom: 4px;
            line-height: 1;
        }
        
        .stage-text {
            line-height: 1.1;
            word-wrap: break-word;
            overflow: hidden;
            font-size: 0.9em;
        }
        
        .pathway {
            position: absolute;
            border: 2px dashed #8B4513;
            opacity: 0.4;
            z-index: 1;
        }
        
        .pathway-divine {
            top: 100px;
            left: 50%;
            width: 2px;
            height: 100px;
            transform: translateX(-50%);
        }
        
        .pathway-internal {
            top: 35%;
            left: 90px;
            width: 100px;
            height: 2px;
            transform: translateY(-50%);
        }
        
        .pathway-external {
            top: 65%;
            left: 90px;
            width: 100px;
            height: 2px;
            transform: translateY(-50%);
        }
        
        .pathway-creation {
            top: 50%;
            right: 90px;
            width: 100px;
            height: 2px;
            transform: translateY(-50%);
        }
        
        .pathway-time {
            bottom: 100px;
            left: 50%;
            width: 2px;
            height: 100px;
            transform: translateX(-50%);
        }
        
        .garden-features {
            margin-top: 120px;
            background: linear-gradient(135deg, #f1f8e9 0%, #aed581 100%);
            border: 2px solid #689f38;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
        }
        
        .garden-tools {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin: 20px 0;
            flex-wrap: wrap;
        }
        
        .tool-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 8px;
        }
        
        .garden-tool {
            filter: drop-shadow(2px 2px 4px rgba(0,0,0,0.2));
            transition: transform 0.3s ease;
        }
        
        .garden-tool:hover {
            transform: scale(1.1);
        }
        
        .tool-label {
            font-size: 0.9em;
            color: #33691e;
            font-weight: bold;
        }
        
        .features-title {
            font-weight: bold;
            color: #33691e;
            margin-bottom: 15px;
            font-size: 1.2em;
        }
        
        .feature-list {
            font-size: 0.9em;
            color: #558b2f;
            line-height: 1.6;
            max-width: 600px;
            margin: 0 auto;
            word-wrap: break-word;
        }
        
        @media (max-width: 900px) {
            .circular-garden {
                width: 600px;
                height: 600px;
            }
            
            .growing-bed {
                width: 200px;
                height: 130px;
                padding: 15px;
            }
            
            .bed-divine {
                top: -65px;
            }
            
            .bed-internal {
                top: 120px;
                left: -100px;
            }
            
            .bed-external {
                top: 350px;
                left: -100px;
            }
            
            .bed-creation {
                top: 120px;
                right: -100px;
            }
            
            .bed-time {
                bottom: -65px;
            }
        }
        
        @media (max-width: 768px) {
            .circular-garden {
                width: 500px;
                height: 500px;
            }
            
            .central-hub {
                width: 140px;
                height: 140px;
                padding: 12px;
            }
            
            .hub-title {
                font-size: 0.9em;
            }
            
            .hub-subtitle {
                font-size: 0.65em;
            }
            
            .prayer-circle {
                width: 120px;
                height: 120px;
            }
            
            .growing-bed {
                width: 180px;
                height: 120px;
                padding: 12px;
            }
            
            .bed-title {
                font-size: 0.9em;
            }
            
            .bed-subtitle {
                font-size: 0.7em;
            }
            
            .growth-stage {
                font-size: 0.65em;
            }
            
            .stage-icon {
                font-size: 1.2em;
            }
            
            .bed-divine {
                top: -60px;
            }
            
            .bed-internal {
                top: 100px;
                left: -90px;
            }
            
            .bed-external {
                top: 280px;
                left: -90px;
            }
            
            .bed-creation {
                top: 100px;
                right: -90px;
            }
            
            .bed-time {
                bottom: -60px;
            }
            
            .journey-steps {
                flex-direction: column;
                align-items: center;
            }
            
            .journey-step {
                max-width: 280px;
                width: 100%;
            }
            
            .legend-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="garden-container">
        <h1 class="garden-title">🌱 JSJ's Digital Allotment</h1>
        <p class="garden-subtitle">A digital pick-your-own for growing healthy churches</p>
        
        <div class="user-journey">
            <div class="journey-title">🚶‍♀️ Enjoying your visit to the digital allotment</div>
            <div class="journey-steps">
                <div class="journey-step">
                    <span class="step-number">1.</span> Come on in, simply because you are curious, or bring a question with you
                </div>
                <div class="journey-step">
                    <span class="step-number">2.</span> Visit the prayer hub at the centre of the allotment
                </div>
                <div class="journey-step">
                    <span class="step-number">3.</span> Check out each of the beds for something that catches your eye
                </div>
                <div class="journey-step">
                    <span class="step-number">4.</span> Fill your trug with as much you can cook, or as much as you need
                </div>
                <div class="journey-step">
                    <span class="step-number">5.</span> Check out the growing guides and the recipes
                </div>
                <div class="journey-step">
                    <span class="step-number">6.</span> Cook, chew, enjoy, feast together, or plant, tend and harvest later
                 </div>
            </div>
        </div>
        
        <div class="legend">
            <div class="legend-title">Growing Guide - Here are plants you will find</div>
            <div class="legend-grid">
                <div class="legend-item">
                    <span class="legend-icon">🌱</span>
                    <span class="legend-text">Seedling: Experimental ideas needing development</span>
                </div>
                <div class="legend-item">
                    <span class="legend-icon">🌿</span>
                    <span class="legend-text">Growing: Promising practices being tested</span>
                </div>
                <div class="legend-item">
                    <span class="legend-icon">🌸</span>
                    <span class="legend-text">Flowering: Developed methods ready for adaptation</span>
                </div>
                <div class="legend-item">
                    <span class="legend-icon">🍇</span>
                    <span class="legend-text">Fruit-bearing: Proven practices with implementation guides</span>
                </div>
            </div>
        </div>
        
        <div class="circular-garden">
            <div class="central-hub">
                <div class="hub-title">🙏 Prayer Integration Hub</div>
                <div class="hub-subtitle">Contemplative practices connecting all relationships</div>
                <div class="prayer-circle"></div>
            </div>
            
            <div class="pathway pathway-divine"></div>
            <div class="pathway pathway-internal"></div>
            <div class="pathway pathway-external"></div>
            <div class="pathway pathway-creation"></div>
            <div class="pathway pathway-time"></div>
            
            <div class="growing-bed bed-divine">
                <a href="/relationship-with-god" class="bed-title">Our Relationship with God</a>
                <div class="bed-subtitle">Sacred encounters & worship</div>
                <div class="growth-indicators">
                    <div class="growth-stage">
                        <div class="stage-icon">🌱</div>
                        <div class="stage-text">Prayer</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌿</div>
                        <div class="stage-text">Worship</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌸</div>
                        <div class="stage-text">Scripture</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🍇</div>
                        <div class="stage-text">Authority</div>
                    </div>
                </div>
            </div>
            
            <div class="growing-bed bed-internal">
                <a href="/internal-community" class="bed-title">Internal Community Relationships</a>
                <div class="bed-subtitle">Identity & belonging within</div>
                <div class="growth-indicators">
                    <div class="growth-stage">
                        <div class="stage-icon">🌱</div>
                        <div class="stage-text">Identity</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌿</div>
                        <div class="stage-text">Authority</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌸</div>
                        <div class="stage-text">Conflict</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🍎</div>
                        <div class="stage-text">Discipleship</div>
                    </div>
                </div>
            </div>
            
            <div class="growing-bed bed-external">
                <a href="/external-community" class="bed-title">External Community Relationships</a>
                <div class="bed-subtitle">Mission & public witness</div>
                <div class="growth-indicators">
                    <div class="growth-stage">
                        <div class="stage-icon">🌱</div>
                        <div class="stage-text">Mission</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌿</div>
                        <div class="stage-text">Justice</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌸</div>
                        <div class="stage-text">Civic</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌍</div>
                        <div class="stage-text">Networks</div>
                    </div>
                </div>
            </div>
            
            <div class="growing-bed bed-creation">
                <a href="/relationship-with-creation" class="bed-title">Our Relationship with Creation</a>
                <div class="bed-subtitle">Place & stewardship</div>
                <div class="growth-indicators">
                    <div class="growth-stage">
                        <div class="stage-icon">🌱</div>
                        <div class="stage-text">Place</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌿</div>
                        <div class="stage-text">Resources</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌸</div>
                        <div class="stage-text">Justice</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌾</div>
                        <div class="stage-text">Economics</div>
                    </div>
                </div>
            </div>
            
            <div class="growing-bed bed-time">
                <a href="/relationship-with-time" class="bed-title">Our Relationship with Time & Memory</a>
                <div class="bed-subtitle">Tradition & creative expression</div>
                <div class="growth-indicators">
                    <div class="growth-stage">
                        <div class="stage-icon">🌱</div>
                        <div class="stage-text">Memory</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌿</div>
                        <div class="stage-text">Tradition</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">🌸</div>
                        <div class="stage-text">Arts</div>
                    </div>
                    <div class="growth-stage">
                        <div class="stage-icon">⭐</div>
                        <div class="stage-text">Future</div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="garden-features">
            <div class="features-title">🧺 Garden Features</div>
            <div class="garden-tools">
                <div class="tool-container">
                    <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wAARCAA8AHgDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD2+iiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigD/2Q==" alt="Trug - Fill your trug" class="garden-tool" width="60" height="60">
                    <span class="tool-label">Fill your trug</span>
                </div>
                <div class="tool-container">
                    <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wBDAAYEBQYFBAYGBQYHBwYIChAKCgkJChQODwwQFxQYGBcUFhYaHSUfGhsjHBYWICwgIyYnKSopGR8tMC0oMCUoKSj/2wBDAQcHBwoIChMKChMoGhYaKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCgoKCj/wAARCAA8AHgDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD2+iiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAoooo